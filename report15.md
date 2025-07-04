Observation: | Function Name | Input Parameters | Output Parameters | Purpose |
| --- | --- | --- | --- |
| userExists | String username | boolean | Checks if a user exists in the database |
| readFile | String filename | String | Reads the contents of a file |
| doStuff | int a, int b | int | Performs an unclear operation on two integers |
| printUpperCase | String s |  | Prints a string in uppercase |
| encryptPassword | String password | String | Supposed to encrypt a password, but does not actually do so |

Observation: | Part of Code | Explanation | Proposed Modification |
| --- | --- | --- |
| `private static String DB_PASS = "password";` | Hardcoded password is a security issue | Use environment variables or a secure secrets manager to store sensitive credentials |
| `String sql = "SELECT * FROM users WHERE username = '" + username + "'";` | SQL Injection vulnerability | Use prepared statements with parameterized queries to prevent SQL injection |
| `BufferedReader reader = new BufferedReader(new FileReader(filename));` | No resource close, bad error handling | Use try-with-resources statement to ensure resources are closed, and handle errors properly |
| `if(a > 100) return b / (a - 100);` | Possible divide by zero | Add a check to prevent division by zero, or use a safe division method |
| `System.out.println(s.toUpperCase());` | Null dereference risk | Check for null before calling methods on an object |
| `return password;` | Not actually encrypting | Implement proper encryption using a secure encryption algorithm and key management |

Observation: | Function Name | Maintainability Issues |
| --- | --- |
| userExists | Poor code structure and organization, Inconsistent naming conventions, Low readability, Violation of SOLID principles |
| readFile | Poor code structure and organization, Inconsistent naming conventions, Low readability, Code Duplication |
| doStuff | Poor code structure and organization, Inconsistent naming conventions, Low readability, Violation of SOLID principles |
| printUpperCase | Poor code structure and organization, Inconsistent naming conventions, Low readability |
| encryptPassword | Poor code structure and organization, Inconsistent naming conventions, Low readability, Violation of SOLID principles, Code Duplication |