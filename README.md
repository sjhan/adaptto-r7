# adaptto-r7

export JAVA_HOME=$(/usr/libexec/java_home -v 10)

rm -rf base && \
  /Library/Java/JavaVirtualMachines/jdk-10.jdk/Contents/Home/bin/jlink \
    --add-modules java.se.ee \
    --output base

rm -rf launcher && \
base/bin/java --add-modules java.se.ee --add-opens=java.base/jdk.internal.loader=ALL-UNNAMED --add-opens=java.base/java.net=ALL-UNNAMED \
  -jar ~/.m2/repository/org/apache/sling/org.apache.sling.feature.launcher/0.1.0-SNAPSHOT/org.apache.sling.feature.launcher-0.1.0-SNAPSHOT.jar \
  -f mvn:org.apache.sling/org.apache.sling.adaptto.featuremodel.example/0.0.1/slingfeature/webconsole.http \
  -D felix.systempackages.calculate.uses=true

rm -rf launcher && \
base/bin/java --add-opens=java.base/jdk.internal.loader=ALL-UNNAMED --add-opens=java.base/java.net=ALL-UNNAMED \
  -jar ~/.m2/repository/org/apache/sling/org.apache.sling.feature.launcher/0.1.0-SNAPSHOT/org.apache.sling.feature.launcher-0.1.0-SNAPSHOT.jar \
  -f mvn:org.apache.sling/org.apache.sling.adaptto.featuremodel.example/0.0.1/slingfeature/webconsole.http \
  -D felix.systempackages.calculate.uses=true

rm -rf base && \
  /Library/Java/JavaVirtualMachines/jdk-10.jdk/Contents/Home/bin/jlink \
    --add-modules java.base,java.logging,java.xml.ws.annotation,java.management,java.naming,java.rmi,java.xml \
    --output base

rm -rf launcher && \
base/bin/java --add-opens=java.base/jdk.internal.loader=ALL-UNNAMED --add-opens=java.base/java.net=ALL-UNNAMED \
  -jar ~/.m2/repository/org/apache/sling/org.apache.sling.feature.launcher/0.1.0-SNAPSHOT/org.apache.sling.feature.launcher-0.1.0-SNAPSHOT.jar \
  -f mvn:org.apache.sling/org.apache.sling.adaptto.featuremodel.example/0.0.1/slingfeature/webconsole.http \
  -D felix.systempackages.calculate.uses=true

rm -rf launcher && \
base/bin/java --add-opens=java.base/jdk.internal.loader=ALL-UNNAMED --add-opens=java.base/java.net=ALL-UNNAMED \
  -jar ~/.m2/repository/org/apache/sling/org.apache.sling.feature.launcher/0.1.0-SNAPSHOT/org.apache.sling.feature.launcher-0.1.0-SNAPSHOT.jar \
  -f mvn:org.apache.sling/org.apache.sling.adaptto.featuremodel.example/0.0.1/slingfeature/webconsole.http \
  -D felix.systempackages.calculate.uses=true -fv 5.6.10

du -h -d0 base
