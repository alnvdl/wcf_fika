# WCF Fika

A [fika](https://en.wikipedia.org/wiki/Fika_%28Sweden%29) management
application for [WebCLIFramework](https://github.com/alnvdl/wcf).

This application was originally the motivation for the creation of the
WebCLIFramework: I needed a way to manage fika in the team I work. We
previously used a manual process involving paper clips and plastic boxes,
which was OK but could use some excessive use of technology to make it more
fun.

The system is governed by the following rules:

1. Everyone has some funds ("cake coins");
2. Whoever has the least funds has to host the next fika session. In case of a
   tie, the names of the people involved in the tie are sorted alphabetically
   (a, b, c...), and whoever is first has to host the next fika session;
3. When someone joins a fika session hosted by another person, they must pay 1
   cake coin;
4. In case someone cannot host a fika session when they are due, they must
   reach an agreement with someone else (usually the next in line);
5. There's a default, universally agreed number of cake coins granted to new
   team members when they join the system.

And this is a typical workflow:

1. Whoever is hosting fika starts a session (`fika start`)
2. Other people participating in this fika session must join (`fika join
    [someone]`)
3. When the session ends, the host is responsible for closing it by issuing a
command twice (`fika end`)

When the session ends, funds are collected and transferred automaticaly by the
system.

Fika commands involving hosting and fund transfers require the user to be
logged in before. See the
[WebCLIFramework](https://github.com/alnvdl/wcf) documentation to understand 
what that means and the implications.

## Installing
1. Go to your WCF folder and run:
    ```sh
    $ npm install https://github.com/alnvdl/wcf_fika.git
    ```

2. Edit the `config.json` file in your WCF folder and include this module in
the `apps` settting:
    ```json
    {
        ...
        "apps": [
            ...,
            "wcf_fika/fika"
        ]
    }
    ```

3. Restart the server and use the `fika` application. Try the `fika help`
command to learn more about what can be done. You will need to login (using the
`login` application) before using any useful `fika` functionality.

In order to use the `login` application, you'll need to create some users
before. See the [WebCLIFramework](https://github.com/alnvdl/wcf) documentation 
to learn how to do that.

## ToDo

- Funds transfer between any two users. This should create a parallel economy :)
- Email notifications informing everyone about the next hosts
- Statistics
- Proper testing

Pull requests are welcome.
