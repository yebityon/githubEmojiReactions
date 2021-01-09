# What
A python program to count the emoji reactions in any github repo on issues and issue comments. It is based on queries on the GraphQL Github API V4. 

# Why
For emojis! 👍 👎 😄 😕 ❤️ 🎉

# How to run the example
Create file githubtoken_Example.py to githubToken.py. Get your own token from Github and fill it to bearerToken following this [link](https://help.github.com/articles/creating-a-personal-access-token-for-the-command-line/)

we need Docker to implement this project. Please  install docker for mac [link](https://hub.docker.com/editions/community/docker-ce-desktop-mac)

Make sure that all python code move to /opt.

```bash
docker-compose up -d --build
docker-compose exec python3 bash
```
f
As you will see from the result, it does handle the edge case where there are more than 100 emojis under a comment. You can verify this with repo denoland/deno issue 25. 

It also handles the limitation of Github API where you have a quota on the number of requests per hour. The program will sleep when it almost hits the limit and it will resume after one hour when the quota is renewed. 

# Use the code as a library 
```python
from fetchData import getReactions
result = getReactions('denoland', 'deno')
```



