Создал папку
mkdir my-site
cd my-site

Создал файл index.html:

<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>My Site</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>Hello, World!</h1>
    <p>This is my first website.</p>
    <script src="script.js"></script>
</body>
</html>

Создал файл style.css:

body {
    background-color: #e6e6e6;
    font-family: sans-serif;
}

h1 {
    color: #333;
}

p {
    color: #666;
}

Создал файл script.js:
console.log("Hello, World!");

Создал файл Dockerfile:
FROM nginx
COPY . /usr/share/nginx/html


Затем:
docker build -t my-site-image .

docker run -d -p 80:80 my-site-image

Перейти на http://localhost