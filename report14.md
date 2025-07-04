# Function Analysis
| Function Name | Parameters | Return Type | Description |
| --- | --- | --- | --- |
| userExists | String username | boolean | Returns true if user exists, false otherwise |
| readFile | String filename | String | Reads a file and returns its contents |
| doStuff | int a, int b | int | Poorly named method, unclear purpose |
| printUpperCase | String s | void | Prints the input string in upper case |
| encryptPassword | String password | String | TODO: Implement encryption (never done) |

## Risk Analysis
| Code | Explanation | Proposed Modification |
| --- | --- | --- |
| `private static String DB_PASS = "password";` | Hardcoded password is a security issue | Use environment variables or a secure secrets manager to store sensitive credentials |
| `String sql = "SELECT * FROM users WHERE username = '" + username + "'";` | SQL Injection vulnerability | Use prepared statements with parameterized queries to prevent SQL injection |
| `BufferedReader reader = new BufferedReader(new FileReader(filename));` | Resource not closed | Use try-with-resources statement to ensure resources are closed |
| `catch(IOException e) { // Silently ignore errors }` | Bad error handling | Log or handle exceptions properly to avoid silent failures |
| `public static int doStuff(int a, int b) { if(a > 100) return b / (a - 100); // possible divide by zero }` | Possible divide by zero | Add input validation to prevent division by zero |
| `public static void printUpperCase(String s) { System.out.println(s.toUpperCase()); }` | Null dereference risk | Add null check before calling `toUpperCase()` method |
| `public static String encryptPassword(String password) { // Not actually encrypting! return password; }` | TODO: Implement encryption (never done) | Implement proper encryption using a secure algorithm and library |

## Maintainability Analysis
Observation: | Function Name | Maintainability Issue |
| --- | --- |
| userExists | poor code structure and organization, inconsistent naming conventions, low readability, violation of SOLID principles |
| readFile | poor code structure and organization, inconsistent naming conventions, low readability, code duplication |
| doStuff | poor code structure and organization, inconsistent naming conventions, low readability, code duplication |
| printUpperCase | poor code structure and organization, inconsistent naming conventions, low readability, code duplication |
| encryptPassword | poor code structure and organization, inconsistent naming conventions, low readability, code duplication |