
1. Install Docker, Docker-compose and colima
1. Install graalvm and native-image
1. export JAVA_HOME=/Library/Java/JavaVirtualMachines/graalvm-22.jdk/Contents/Home
1. export PATH=/Library/Java/JavaVirtualMachines/graalvm-22.jdk/Contents/Home/bin:$PATH
1. export DOCKER_HOST=unix://$HOME/.colima/default/docker.sock
1. export TESTCONTAINERS_DOCKER_SOCKET_OVERRIDE=/var/run/docker.sock
1. Edit /Users/ldesrosi/.testcontainers.properties --> testcontainers.reuse.enable=true
1. Download BAMOE samples and unzip under build/src
1. Build maven repo image
1. Start maven repo image
1. cd src & mvn install
For jppm-compact-architecture-example-service, process-monitoring-quarkus and dmn-drools-quarkus-metrics
1. mvn clean package -Pcontainer
1. docker push
For kogito-travel
1. mvn package -Pnative -Dnative-image.docker-build=true
1. docker build -f src/main/docker/Dockerfile.native -t quarkus/using-kogito .