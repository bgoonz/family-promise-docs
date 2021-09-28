---
description: 'https://app.gitbook.com/invite/lambda-labs?invite=-Mki0Tg1b0WL4B6KHgL5'
---

# Initial page

## Contact Info:

| Name | Role | Github | Linkedin | Number | Time Zone |
| :--- | :--- | :--- | :--- | :--- | :--- |
|  |  |  |  |  |  |
| Bryan Guner | UX | [https://github.com/bgoonz](https://github.com/bgoonz) | [https://www.linkedin.com/in/bryan-guner-046199128/](https://www.linkedin.com/in/bryan-guner-046199128/) | 551-254-5505 | EST |









## Labs Engineering Docs

## Labs Guides <a id="labs-guides"></a>

* ​[Labs Engineering Standards](https://docs.labs.lambdaschool.com/standards/)​
* ​[Labs Engineering Guide](https://docs.labs.lambdaschool.com/guides/)​
* ​[Labs Data Science Guide](https://docs.labs.lambdaschool.com/data-science/)​

## Labs Scaffolding <a id="labs-scaffolding"></a>

* ​[Labs SPA Starter](https://docs.labs.lambdaschool.com/labs-spa-starter/)​
* ​[Labs API Starter](https://docs.labs.lambdaschool.com/api/)​

## Please read this carefully! <a id="please-read-this-carefully"></a>

The internet is full of very powerful platforms for supporting your application \(AWS, Heroku, etc.\). These platforms require the use of secrets \(passwords, keys, tokens, etc.\) to access and use their services.

🎗 It is your responsibility to always protect the secret keys and tokens you use to access these platforms. A single compromise of your application resources can have major a significant impact on the life of your application and potentially on the lives of people affected.

🔐 Always protect your secrets! The secrets you use to access these services should be protected at all times with extreme care! Exposing secrets to anyone not entitled to have them can hurt your career, your product, your company, your colleagues and in many cases the public.

❌ Never commit your secrets to a code repository! This is the most common mistake that you can make when handling secrets. You will never need to or should commit a secret to a code repository for any reason whatsoever.

🔒 Keep your secrets hidden! Your secrets should never be hardcoded into your application code. Instead, they must always be passed to your code after your code is running. Every platform you use will have some mechanism for passing secrets to your code at runtime. In general, the system environment is where you should get your secrets after your application starts up.

👀 Heroku provides a mechanism for getting runtime variables to your application after it is running, which is how you should be getting your secrets to your application: [https://devcenter.heroku.com/articles/config-vars](https://devcenter.heroku.com/articles/config-vars)​

The AWS security team scans for AWS keys in public repositories. If they find them, they notify the Lambda School engineering team who will rotate the keys and may lock out individual students or the entire team. Please be very careful not to commit secrets into your repository.

💥 Please be careful, you are responsible!

If you cannot think of a way to get your secrets to your application without hardcoding... stop! Talk to your TPL, APL or an Engineering Manager for a solution. Please do not ever commit your secret keys into your code repository or expose them in any other way.

Install git-secrets right now! All students using Git are required to install git-secrets \([https://github.com/awslabs/git-secrets](https://github.com/awslabs/git-secrets)\) which will greatly reduce the possibility of pushing secrets to your code repository. All students are should install and use git-secrets while working in Labs. Of course, it's also a good idea to use git-secrets whenever and wherever you're writing code. Be sure to follow the Advanced Configuration steps to be sure that all current and new repos have git-secrets enabled.

Install dotenv right now! You can use dotenv or another similar tool to automatically load secrets and other runtime parameters as your application starts. These tools help to keep secrets safe by ensuring they can be easily loaded without needing to hardcode them. Be sure to that the .env file is in your .gitignore file.

Never commit the contents of your .env file to your repository!

Add the line`.env*` to your`.gitignore`file to be sure you never accidentally commit a `.env` file.

Never hardcode any secrets! Don't do it! Not even for a minute for a quick test! Chances are you'll be so happy your code works you'll forget about the hardcoded key, commit the code, push it to GitHub and will get your app shutdown or pwned and all your data exposed and your commit of a secret key will be forever tied to your GitHub ID. Use dotenv to be make managing secrets easier and use git-secrets to prevent accidents.

Don't ignore or hide mistakes! If you mess up, it's fine! The only thing that makes it not fine is if you try to hide your mistake. We might not find it, but someone will. If you expose a secret by pushing it to a repo, let your TPL or APL know immediately. We can then invalidate the secret \(change the password, rotate the key\) and move on.

