## Description

`django-vue-google-auth` shows how you can implement authentication through Google using **django & django rest framework** as a backend and **vue.js** as a frontend.

## How to run

Clone the repository:

```zsh
➜ git clone https://github.com/apirobot/django-vue-google-auth
```

Install dependencies:

```zsh
../backend  ➜  pipenv install
../frontend ➜  npm install
```

Run migrations:

```zsh
../backend ➜  python manage.py makemigrations
../backend ➜  python manage.py migrate
```

Start up backend:

```zsh
../backend ➜  python manage.py runserver
```

Start up frontend:

```zsh
../frontend ➜  npm start
```

We are done.

- Frontend: http://localhost:8080/
- Backend: http://localhost:8000/
