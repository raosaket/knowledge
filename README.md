# Knowledge
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Article Website</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }

        body {
            line-height: 1.6;
            color: #333;
            background-color: #f4f4f4;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        header {
            background: #333;
            color: #fff;
            padding: 1rem 0;
            margin-bottom: 2rem;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        nav ul {
            display: flex;
            list-style: none;
        }

        nav ul li {
            margin-left: 2rem;
        }

        nav a {
            color: #fff;
            text-decoration: none;
        }

        .article-form {
            background: #fff;
            padding: 2rem;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            margin-bottom: 2rem;
        }

        .article-form h2 {
            margin-bottom: 1rem;
        }

        .form-group {
            margin-bottom: 1rem;
        }

        input[type="text"],
        textarea {
            width: 100%;
            padding: 0.5rem;
            border: 1px solid #ddd;
            border-radius: 4px;
        }

        button {
            background: #333;
            color: #fff;
            border: none;
            padding: 0.7rem 1.5rem;
            border-radius: 4px;
            cursor: pointer;
        }

        .articles-list {
            background: #fff;
            padding: 2rem;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }

        .article {
            margin-bottom: 2rem;
            padding-bottom: 1rem;
            border-bottom: 1px solid #eee;
        }

        .article h3 {
            color: #333;
            margin-bottom: 0.5rem;
        }

        .article-meta {
            color: #666;
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .article-content {
            color: #444;
        }
    </style>
</head>
<body>
    <header>
        <nav class="container">
            <h1>My Articles</h1>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main class="container">
        <section class="article-form">
            <h2>Write a New Article</h2>
            <form id="articleForm">
                <div class="form-group">
                    <input type="text" placeholder="Article Title" required>
                </div>
                <div class="form-group">
                    <input type="text" placeholder="Author Name" required>
                </div>
                <div class="form-group">
                    <textarea placeholder="Write your article here..." rows="10" required></textarea>
                </div>
                <button type="submit">Publish Article</button>
            </form>
        </section>

        <section class="articles-list">
            <h2>Latest Articles</h2>
            
            <div class="article">
                <h3>Sample Article Title</h3>
                <div class="article-meta">
                    Posted by John Doe on January 1, 2023
                </div>
                <div class="article-content">
                    <p>This is a sample article content. You can write your own articles using the form above. Lorem ipsum dolor sit amet consectetur adipisicing elit. Quisquam, voluptatum.</p>
                </div>
            </div>

            <!-- More articles will be added here dynamically -->
        </section>
    </main>

    <script>
        // Simple form handling (you'll need to implement proper backend processing)
        document.getElementById('articleForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const title = this.querySelector('input[type="text"]:first-of-type').value;
            const author = this.querySelector('input[type="text"]:last-of-type').value;
            const content = this.querySelector('textarea').value;
            
            const articleList = document.querySelector('.articles-list');
            const newArticle = document.createElement('div');
            newArticle.className = 'article';
            newArticle.innerHTML = `
                <h3>${title}</h3>
                <div class="article-meta">
                    Posted by ${author} on ${new Date().toLocaleDateString()}
                </div>
                <div class="article-content">
                    <p>${content}</p>
                </div>
            `;
            
            articleList.insertBefore(newArticle, articleList.firstChild.nextSibling);
            
            this.reset();
        });
    </script>
</body>
</html>
