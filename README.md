# Testing Quarkus

## setup env

```
curl -Ls https://sh.jbang.dev | bash -s - trust add https://repo1.maven.org/maven2/io/quarkus/quarkus-cli/
curl -Ls https://sh.jbang.dev | bash -s - app install --fresh --force quarkus@quarkusio

sudo dnf -y install maven
```

## build, packaging and running

```
cd code-with-quarkus
mvn compile quarkus:dev
mvn package
java -jar target/quarkus-app/quarkus-run.jar
```

open http://0.0.0.0:8080/


### native

```
quarkus build --native
mvn verify -Pnative
quarkus build --native -Dquarkus.native.container-build=true
package -Pnative -Dquarkus.native.container-build=true -Dquarkus.container-image.build=true

docker build -f src/main/docker/Dockerfile.native-micro -t quarkus/code-with-quarkus .
```

open http://0.0.0.0:8080/


## links
* https://quarkus.io/

