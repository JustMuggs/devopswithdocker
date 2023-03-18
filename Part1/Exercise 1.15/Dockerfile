# Get a java image
FROM openjdk:8
# Open port 8080
EXPOSE 8080
# Copy files to selected dir
WORKDIR /usr/src/app
COPY . .
# Edit the 'mvnw' file for Windows
RUN sed -i 's/\r$//' mvnw
# Run 'mvnw' file
RUN ./mvnw package
CMD ["java", "-jar", "./target/docker-example-1.1.3.jar"]
