**Title:** Sensitive Information Disclosure – Plaintext Credentials Exposed in /db/drug_recommendor.sql

**Severity:** High

**CWE:** CWE-200 – Exposure of Sensitive Information to an Unauthorized Actor

**Researchers:** Karan Parelkar, Anubhav Verma, Parth Desai

**Summary**

During security testing of the open-source Drug Recommendor project, plaintext credentials were found in the publicly distributed database file:

**/db/drug_recommendor.sql**

The credentials are accessible by simply downloading and opening the SQL file, without authentication or exploitation.

**Steps to Reproduce**

1. Navigate to /db/.

![POC](images/sql%20file%201.png)

2. Click on drug_recommender.sql
   
![POC](images/sql%20file%201.png)

3. Open drug_recommendor.sql in VS Code or any text editor.
   
![POC](images/sql%20file%202.png)

4. Credential information can be observed directly in the SQL dump.

![POC](images/sql%20file%203.png)

**Impact**

An attacker who obtains valid credentials may potentially gain unauthorized access to the associated application/account and sensitive information.

**Remediation**

Remove credentials from publicly distributed SQL dumps.

Replace them with dummy/test credentials.

Never store passwords in plaintext; use bcrypt/Argon2id.

Rotate any credentials that have already been exposed.
