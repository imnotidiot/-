from flask import Flask, render_template

app = Flask(__name__)

# Define routes
@app.route("/")
def home():
    return render_template("home.html")

@app.route("/about")
def about():
    return render_template("about.html")

@app.route("/portfolio")
def portfolio():
    projects = [
        {
            "name": "Project 1",
            "description": "Lorem ipsum dolor sit amet, consectetur adipiscing elit.",
            "image": "project1.jpg",
            "url": "https://github.com/yourusername/project1"
        },
        {
            "name": "Project 2",
            "description": "Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
            "image": "project2.jpg",
            "url": "https://github.com/yourusername/project2"
        },
        {
            "name": "Project 3",
            "description": "Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
            "image": "project3.jpg",
            "url": "https://github.com/yourusername/project3"
        }
    ]
    return render_template("portfolio.html", projects=projects)

if __name__ == "__main__":
    app.run(debug=True)
