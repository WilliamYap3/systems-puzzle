Steps to debug the system
1) Inside the "Dockerfile" file, change "EXPOSE 5001" to "EXPOSE 8080"
2) Inside the "docker-compose.yml" file, change "80:8080" to "8080:80"
3) Inside the "flaskapp.conf" file, change "proxy_pass http://flaskapp:5001" to "proxy_pass http://flaskapp:80"
4) Inside the "app.py" file, add "port=80" to the "app.run" function
5) Inside the "templates" folder, create a "displayitems.html" template which will display each item in the query.
6) Inside the "app.py" file, change "return str(results)" to "return render_template('displayitems.html', results=results)"
