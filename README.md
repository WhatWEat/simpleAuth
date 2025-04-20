# Test by Apifox

## 1. Login Request (`/api/login`)

- **Method**: `POST`
- **URL**: `/api/login`
- **Body** (raw JSON):
  ```json
  {
    "username": "test",
    "password": "123456"
  }
  ```

- **Expected Response**:
  - `200 OK` if credentials are valid.
  - Includes a `Set-Cookie` header:
    ```
    Set-Cookie: JSESSIONID=your-session-id
    ```

## 2. Hello (`/api/hello`)

- **Method**: `GET`
- **URL**: `/api/hello`
- **Headers**:
  - Add a `Cookie` header with the value of `JSESSIONID` from the login response:
    ```
    Cookie: JSESSIONID=your-session-id
    ```

- **Expected Response**:
  ```
  Hello World
  ```
