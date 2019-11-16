Building a Single Command Application
#####################################

When building a command line tool, you may not need to provide several commands.
In such case, having to pass the command name each time is tedious. Fortunately,
it is possible to remove this need by using `default()` when adding a command:

.. code-block:: python

    from cleo import Application

    command = GreetCommand()

    app = Application()
    app.add(command)
    app.set_default_command("greet", is_single_command=True)

    # this now executes the 'GreetCommand' without passing its name
    app.run()
