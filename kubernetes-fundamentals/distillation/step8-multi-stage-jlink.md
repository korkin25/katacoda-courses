Consider this definition.

`cat packaging/Dockerfile-multi-stage-jlink`{{execute}}

Notice the two FROM statements. The first FROM declares a container that is big and contains a Java compiler. The stage contains has all the dependencies that can compile the should code, run Gradle and produce the jar file. However this first container is much too bloated and filled with tools we would never use in production. The second FROM defines the final container and it's the smaller Alpine instance that will simply hold the JRE and jar of the application. The key line is the `COPY --from=builder` that transmits the artifact output of the first _build_ container into the last _Alpine_ container. During the container build both containers are used, however the final container image will only include the containers defined in the _last_ FROM stage. Distillation and idempotency achieved.

Build the ListDir application with the multi-stage build.

`docker build \
-f packaging/Dockerfile-multi-stage-jlink \
-t $REGISTRY/listdir-d-ms-jlink:0.1.0 \
.`{{execute}}

After a few moments a new container is built.

`docker images $REGISTRY/listdir*`{{execute}}

Push it to the private registry.

`docker push $REGISTRY/listdir-d-ms-jlink:0.1.0`{{execute}}

Notice the size of the binary container image is ... TODO

Let's see how long the execution will take.

`time docker run $REGISTRY/listdir-d-ms-jlink:0.1.0`{{execute}}

run it a few more times and see what the average time is the same as the previous step. The image is not smaller nor does it run faster, but the multi-stage feature will be used in the upcoming steps.