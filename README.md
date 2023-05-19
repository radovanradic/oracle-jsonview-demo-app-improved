This is sample for Micronaut Data using Oracle Json Duality View.

It uses test container with docker image "gvenzl/oracle-free:latest-faststart" by default and then
datasource configuration is taken from the container before starting Micronaut application context. To get started run the application:

```
./gradlew run
```

When app is ready, to list all students, use this:
```
curl http://localhost:8080/students
```
To find student by id:
```
curl http://localhost:8080/students/1
```
Find student by name:
```
curl http://localhost:8080/students/student/Fred
```
Create new student with classes
```
curl -d '{"student":"Peter", "averageGrade":9.8, "classes": ["Math", "English"]}' -H "Content-Type: application/json" -X POST http://localhost:8080/students
```
To update student average grade
```
curl -X PUT http://localhost:8080/students/1/average_grade/9.8
```
Find max average grade:
```
curl http://localhost:8080/students/max_average_grade
```
Update student name:
```
curl -X PUT http://localhost:8080/students/1/student/NewName
```
In order to delete student by id
```
curl -X DELETE http://localhost:8080/students/1
```