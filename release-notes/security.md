# Security

The following list of major security enhancements have been implemented within the 2.4 release:



| **Issue**                                                                             | **Description**                                                                                                                      | **Resolution**                                                                                   |
| ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ |
| [WIFI-3585](https://telecominfraproject.atlassian.net/browse/WIFI-3585)               | Password reset and email verification procedures can be exploited by an adversary that acquired a user ID                            | Hardened action link generation with UUIDs                                                       |
| [WIFI-6011](https://telecominfraproject.atlassian.net/browse/WIFI-6011)               | Cloud services do not log sensitive events occurred during runtime                                                                   | Implemented security logs to collect evidence that can help with incident investigation          |
| [WIFI-5615](https://telecominfraproject.atlassian.net/browse/WIFI-5615)               | Weak password hash computation is vulnerable to rainbow table attacks                                                                | Hardened password hash computation with salting                                                  |
| [WIFI-5616](https://telecominfraproject.atlassian.net/browse/WIFI-5616)               | Hardcoded default password is vulnerable to password guessing attacks                                                                | Implemented password change procedure on first login and replaced hardcoded password with a hash |
| [WIFI-5617](https://telecominfraproject.atlassian.net/browse/WIFI-5617)               | Some API responses leak user secrets by revealing password hashes                                                                    | Removed password hashes from API responses                                                       |
| [WIFI-5618](https://telecominfraproject.atlassian.net/browse/WIFI-5618)               | Some API responses reveal server version which can be leveraged by an adversary to compromise it using exploits                      | Removed server version from API responses                                                        |
| [WIFI-5619](https://telecominfraproject.atlassian.net/browse/WIFI-5619)               | API ‘system’ command leak internal file tree by revealing absolute paths of certificate files                                        | Replaced absolute paths of certificates with file names                                          |
| [WIFI-5724](https://telecominfraproject.atlassian.net/browse/WIFI-5724)               | Cloud services are vulnerable to black box exploitation attempts, brute forcing, credential stuffing and DDoS                        | Implemented IP-based rate limit for API endpoints                                                |
| [WIFI-5727](https://telecominfraproject.atlassian.net/browse/WIFI-5727)               | Weak UUID generation with reduced entropy                                                                                            | Hardened UUID by increasing entropy                                                              |
| [WIFI-5772](https://telecominfraproject.atlassian.net/browse/WIFI-5772?src=confmacro) | RTTY-enabled APs can be overtaken by an adversary accessing RTTYS dedicated management interface using default hardcoded credentials | Hardened RTTYS access by randomizing default credentials at deployment                           |

### Known security issues <a href="#major-known-security-issues" id="major-known-security-issues"></a>

* [WIFI-5770](https://telecominfraproject.atlassian.net/browse/WIFI-5770) - RTTYS version used has security flaws which are to be resolved in next releases

