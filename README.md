Shell Manager
=============

Init readme. More to follow.
Packages and deploys problems for CTF platform.

How to package your problem
---------------------------
...


How to use your problem repository
----------------------------------

Add this line to your sources file (`/etc/apt/sources.list`)
```
deb file:///usr/local/ctf-packages ./
```

Problem Format
--------------

Problems consist of three main parts:
1. problem.json
2. problem generators
3. data files
... will be elaborated


#### problem.json

Every problem must contain a problem.json. This file provides metadata about the problem through a series of mandatory and optional fields.
(It would be cool if hints were time sensitive).

| Field | Datatype | Required | Description |
|-------|----------|----------|-------------|
| author | String | Yes | Author of the problem. |
| score | Int | Yes | Points gained for solving the problem. |
| name | String | Yes | The title of the problem on the competition page. |
| description | String Template | Yes | Description for the problem. jinja2 template. |
| category | String | Yes | Category of the problem. |
| version | String | No | Version string for the problem. Defaults to "1.0.0". |
| tags | List[String] | No | Minor descriptors for the problem. |
| hints | List[String] | No | Additional help to the problem. |
| organization | String | No | Organization that the problem identifies with. |
| pkg\_architecture | String | No | Compatible [architectures](https://www.debian.org/doc/debian-policy/ch-controlfields.html#s-f-Architecture). Defaults to "all". |
| pkg\_description | String | No | Description for the deb package. Defaults to `desc`. |
| pkg\_name | String | No | Optional name for the problem package. Defaults to `name`. Check here for the [naming policy](https://www.debian.org/doc/debian-policy/ch-controlfields.html#s-f-Source). |
| pkg\_dependencies | List[String] | No | List of package dependencies. Defaults to none. |
| pip\_requirements | List[String] | No | List of pip requirements for the challenge. Defaults to none. Can alternatively include a `requirements.txt` in your problem directory. |
