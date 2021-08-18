# using-Jinja2
easy Jinja2 templating

```pip install Jinja2``` (for python2)

```pip3 install Jinja2``` (these hold true for linux, please lookup OS specific pip cli arguments)

then in your python file import the following:
```from jinja2 import FileSystemLoader, Environment```

then include the following function:
```def render_from_template(directory, template_name, **kwargs):
    loader = FileSystemLoader(directory)
    env = Environment(loader=loader)
    template = env.get_template(template_name)
    return template.render(**kwargs)
```

and call the function where you would want the HTML string to be output

include in your python file directory a file that uses the Jinja2 syntax, 
default to html (e.g. myTemplate.html)

render the string with the following:
```render_from_template('.', 'myTemplate.html', **data)```
directory, relative file path, args

where data is a dictionary of arguments that looks like this:
    ```data = {
        'arg1': val1,
    }```
