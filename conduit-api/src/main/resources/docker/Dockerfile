FROM openjdk:8-jre-slim
ENV SPRING_DATASOURCE_URL jdbc:mysql://mysql:3306/conduit
ENV SPRING_DATASOURCE_USERNAME root
ENV SPRING_DATASOURCE_PASSWORD password
ENV APP_DIR /app
ARG JAR_FILE
ADD ${JAR_FILE} $APP_DIR/app.jar
WORKDIR $APP_DIR
EXPOSE 8080
CMD ["java", "-Djava.security.egd=file:/dev/./urandom", "-jar","app.jar", "spring.datasource.url=${SPRING_DATASOURCE_URL}", "spring.datasource.username=${SPRING_DATASOURCE_USERNAME}","spring.datasource.password=${SPRING_DATASOURCE_PASSWORD}"]
