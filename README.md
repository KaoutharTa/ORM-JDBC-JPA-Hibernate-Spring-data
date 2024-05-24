# Hospital Management System

## Introduction

This repository contains a Hospital Management System developed using Java and Spring Boot. It provides functionalities to manage patients, doctors, appointments, and consultations within a hospital.

### Entities:

1. **Patient**: Represents individuals visiting the hospital. Includes information such as name, date of birth, and current health status.
2. **Doctor**: Represents medical professionals working at the hospital. Includes information such as name, email, and specialty.
3. **Appointment**: Represents scheduled meetings between patients and doctors. Includes appointment dates and statuses.
4. **Consultation**: Represents sessions where doctors consult with patients. Includes consultation dates and session reports.

## Code Snippets and Explanations

### Entity Classes

#### Consultation.java

```java
@Entity
@Data @NoArgsConstructor @AllArgsConstructor
public class Consultation {
    // Entity fields...
}
```
#### Doctor.java
```java
@Entity
@Data @NoArgsConstructor @AllArgsConstructor
public class Doctor {
    // Entity fields...
}
```
#### Patient.java
```java
@Entity
@Data @NoArgsConstructor @AllArgsConstructor
public class Patient {
    // Entity fields...
}
```
#### RendezVous.java
```java
@Entity
@Data @NoArgsConstructor @AllArgsConstructor
public class RendezVous {
    // Entity fields...
}
```
###Repository Interfaces

<p>The repository part of this Hospital Management System comprises interfaces that extend the JpaRepository interface provided by Spring Data JPA. These interfaces, including ConsultationRepository, MedecinRepository, PatientRepository, and RendezVousRepository, define methods for performing CRUD (Create, Read, Update, Delete) operations on the corresponding entity classes. By extending JpaRepository, these interfaces inherit methods like save(), findById(), findAll(), delete(), etc., enabling convenient data access and manipulation.</p>

#### ConsultationRepository.java
```java
public interface ConsultationRepository extends JpaRepository<Consultation, Long> {
    // Repository methods...
}
```
#### DoctorRepository.java
```java
public interface DoctorRepository extends JpaRepository<Doctor, Long> {
    // Repository methods...
}
```
#### PatientRepository.java
```java
public interface PatientRepository extends JpaRepository<Patient, Long> {
    // Repository methods...
}
```
#### RendezVousRepository.java
```java
public interface RendezVousRepository extends JpaRepository<RendezVous, Long> {
    // Repository methods...
}
```
### Service Interfaces and Implementations
<p>
    On the other hand, the service interfaces and implementations form the core business logic of the system. The IHospital interface declares methods for managing patients, consultations, doctors, and appointments. These methods include savePatient(), saveConsultation(), saveMedecin(), saveRendezVous(), findAll(), findById(), updatePatient(), and deletePatient(). The IHospitalImpl class implements this interface, providing concrete implementations for these methods. It uses the Spring @Service annotation to denote it as a service class, enabling it to be automatically detected and managed by the Spring container. Inside IHospitalImpl, the repositories required for data access are injected using constructor-based dependency injection. Each method in this class corresponds to a specific operation, such as saving or retrieving entities, and it delegates the actual data access tasks to the corresponding repository methods. Additionally, the @Transactional annotation ensures that each method runs within a transactional context, providing consistency and atomicity for database operations. Overall, these service interfaces and implementations encapsulate the business logic and data access operations of the Hospital Management System, promoting modularity, maintainability, and testability.
</p>

####IHospital.java
```java
public interface IHospital {
    // Service methods...
}
```
#### IHospitalImpl.java
```java
@Service
@Transactional
public class IHospitalImpl implements IHospital {
    // Service implementation...
}
```
## Conclusion
The Hospital Management System provides a robust solution for managing patients, doctors, appointments, and consultations within a hospital environment. With structured entity design and repository/service implementations, it offers scalability and maintainability for hospital administrators and staff.
