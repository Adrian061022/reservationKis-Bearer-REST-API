# Learning Platform Bearer REST API Dokumentáció

## Áttekintés

Ez a dokumentáció a **Learning Platform Bearer REST API** működését,
végpontjait és használatát ismerteti.\
A cél egy egységes, biztonságos és bővíthető API kialakítása oktatási
platformok számára.

------------------------------------------------------------------------

## Hitelesítés

Az API **Bearer Token** alapú hitelesítést használ.

### Kérés példája:

    GET /v1/users/me HTTP/1.1
    Host: api.learningplatform.com
    Authorization: Bearer YOUR_ACCESS_TOKEN

------------------------------------------------------------------------

## Alap URL

    https://api.learningplatform.com/v1

------------------------------------------------------------------------

# Végpontok

## 1. Felhasználók

### 🔹 GET /users

Felhasználók listázása.

**Válasz:**

``` json
[
  {
    "id": 1,
    "name": "John Doe",
    "role": "student"
  }
]
```

------------------------------------------------------------------------

### 🔹 GET /users/{id}

Egy felhasználó adatainak lekérése.

------------------------------------------------------------------------

### 🔹 POST /users

Új felhasználó létrehozása.

**Body példa:**

``` json
{
  "name": "Jane Smith",
  "email": "jane@example.com",
  "role": "teacher"
}
```

------------------------------------------------------------------------

## 2. Kurzusok

### 🔹 GET /courses

Az összes kurzus lekérése.

### 🔹 POST /courses

Új kurzus létrehozása.

**Body:**

``` json
{
  "title": "Introduction to AI",
  "description": "Basics of artificial intelligence."
}
```

------------------------------------------------------------------------

## 3. Beiratkozás

### 🔹 POST /enrollments

Felhasználó beiratása egy kurzusra.

**Body:**

``` json
{
  "user_id": 1,
  "course_id": 5
}
```

------------------------------------------------------------------------

## Hibakezelés

Az API egységes hibaformátumot használ:

``` json
{
  "error": "Not Found",
  "message": "Course does not exist",
  "status": 404
}
```

------------------------------------------------------------------------

## Verziózás

Minden végpont a következő struktúrát követi:

    /v1/...

A verziózás új API verziók bevezetését teszi lehetővé kompatibilitási
problémák nélkül.

------------------------------------------------------------------------

# Kapcsolat

További információért vagy hibajelentésért keresd a fejlesztői
csapatot:\
support@learningplatform.com
