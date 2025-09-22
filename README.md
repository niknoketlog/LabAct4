This project demonstrates different types of SQL JOINs exposed through REST API endpoints.

---SQL JOINs Explained:--

- INNER JOIN – Returns rows when there is a match in both tables.  
- LEFT JOIN – Returns all rows from the left table, and matched rows from the right table (NULL if no match).  
- RIGHT JOIN – Returns all rows from the right table, and matched rows from the left table (NULL if no match).  
- FULL OUTER JOIN (emulated with UNION) – Combines LEFT JOIN and RIGHT JOIN to return all rows from both tables.  
- CROSS JOIN – Returns the Cartesian product (all combinations) of rows between two tables.  
- SELF JOIN – Joins a table to itself, useful for hierarchical or referral relationships.  
- JOIN with Subquery – Combines a table with a subquery, such as fetching the latest login per user.

---API Endpoints:---

All endpoints are protected with a valid JWT (`Authorization: Bearer <token>`).

| Endpoint                               | Purpose                                           |
| `GET /api/reports/users-with-roles`    | Users and their roles (INNER JOIN)                |
| `GET /api/reports/users-with-profiles` | Users with optional profile info (LEFT JOIN)      |
| `GET /api/reports/roles-right-join`    | All roles with assigned users (RIGHT JOIN)        |
| `GET /api/reports/profiles-full-outer` | Users + profiles, even when missing matches       |
| `GET /api/reports/user-role-combos`    | Every combination of user and role (CROSS JOIN)   |
| `GET /api/reports/referrals`           | Referrer and referred users (SELF JOIN)           |
| `GET /api/reports/latest-login`        | Latest login per user (LEFT JOIN + subquery)      |
