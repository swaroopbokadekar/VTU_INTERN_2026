Here is a **very small mini-lab** you can demonstrate to students to show **Hibernate + Spring Boot + Entity Relationship (FK)**.

Goal:
Show how a **Transaction table depends on a Master table (Investor)** using **JPA/Hibernate mapping**.

Example:
One **Investor → many Transactions**

---

# Mini Lab: Hibernate Relationship Demo (Spring Boot)

## 1. Concept

We will create:

**Investor (Master Table)**

```
investor_id  (PK)
name
email
```

**Transaction (Child Table)**

```
txn_id (PK)
amount
date
investor_id (FK)
```

Relationship:

```
Investor (1) ----------- (Many) Transaction
```

Hibernate will automatically manage the **foreign key mapping**.

---

# 2. Project Structure

```
hibernate-demo
│
├── entity
│     ├── Investor.java
│     ├── Transaction.java
│
├── repository
│     ├── InvestorRepository.java
│     ├── TransactionRepository.java
│
├── service
│     ├── DemoService.java
│
└── HibernateDemoApplication.java
```

---

# 3. pom.xml (Important Dependencies)

```xml
<dependencies>

<dependency>
<groupId>org.springframework.boot</groupId>
<artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>

<dependency>
<groupId>com.h2database</groupId>
<artifactId>h2</artifactId>
<scope>runtime</scope>
</dependency>

</dependencies>
```

Using **H2 in-memory DB** makes the demo very fast.

---

# 4. application.properties

```
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.driverClassName=org.h2.Driver

spring.jpa.hibernate.ddl-auto=create
spring.jpa.show-sql=true

spring.h2.console.enabled=true
```

Hibernate will **auto-create tables**.

---

# 5. Investor Entity (Master Table)

```java
package com.demo.entity;

import jakarta.persistence.*;

@Entity
public class Investor {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long investorId;

    private String name;
    private String email;

    // getters setters
}
```

Hibernate creates:

```
Investor
--------
investor_id (PK)
name
email
```

---

# 6. Transaction Entity (Child Table)

```java
package com.demo.entity;

import jakarta.persistence.*;

@Entity
public class Transaction {

    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long txnId;

    private double amount;

    private String date;

    @ManyToOne
    @JoinColumn(name="investor_id")
    private Investor investor;

    // getters setters
}
```

Important line:

```
@ManyToOne
@JoinColumn(name="investor_id")
```

Hibernate creates:

```
Transaction
-----------
txn_id (PK)
amount
date
investor_id (FK)
```

---

# 7. Repositories

## InvestorRepository

```java
package com.demo.repository;

import org.springframework.data.jpa.repository.JpaRepository;
import com.demo.entity.Investor;

public interface InvestorRepository extends JpaRepository<Investor, Long> {

}
```

---

## TransactionRepository

```java
package com.demo.repository;

import org.springframework.data.jpa.repository.JpaRepository;
import com.demo.entity.Transaction;

public interface TransactionRepository extends JpaRepository<Transaction, Long> {

}
```

---

# 8. Demo Service

```java
package com.demo.service;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

import com.demo.entity.Investor;
import com.demo.entity.Transaction;
import com.demo.repository.InvestorRepository;
import com.demo.repository.TransactionRepository;

@Service
public class DemoService {

    @Autowired
    InvestorRepository investorRepo;

    @Autowired
    TransactionRepository txnRepo;

    public void runDemo() {

        Investor inv = new Investor();
        inv.setName("Rahul Sharma");
        inv.setEmail("rahul@mail.com");

        investorRepo.save(inv);

        Transaction txn = new Transaction();
        txn.setAmount(50000);
        txn.setDate("2026-03-05");
        txn.setInvestor(inv);

        txnRepo.save(txn);
    }
}
```

Notice this:

```
txn.setInvestor(inv);
```

Hibernate automatically stores the **FK investor_id**.

---

# 9. Run at Application Start

```java
@SpringBootApplication
public class HibernateDemoApplication implements CommandLineRunner {

    @Autowired
    DemoService service;

    public static void main(String[] args) {
        SpringApplication.run(HibernateDemoApplication.class, args);
    }

    @Override
    public void run(String... args) {
        service.runDemo();
    }
}
```

---

# 10. What Students Will See in Console

Hibernate prints SQL:

```
insert into investor (name,email) values (?,?)

insert into transaction (amount,date,investor_id) values (?,?,?)
```

This proves:

**Hibernate handled the Foreign Key automatically.**

---

# 11. What This Demo Teaches (Very Important)

Students learn:

✔ Entity → Table mapping
✔ @Entity
✔ @Id
✔ @GeneratedValue
✔ @ManyToOne relationship
✔ @JoinColumn (Foreign Key)
✔ Hibernate auto SQL generation

---

# 12. 2 Minute Teaching Explanation

You can say:

> "In Hibernate we don't manually write foreign keys.
> We define relationships using annotations like `@ManyToOne`.
> Hibernate automatically creates the FK column and manages the relationship."

