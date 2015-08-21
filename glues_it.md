# WARNING - PLEASE READ
I did not wrote this code. I'm sharing it here for you to benefit. This code was found on a Wordpress plugin.

## Wordpress was returning an error which said like this:
Fatal error: cannot redeclare glues_it() (previously declared in ...

I went ahead and did some research and found out that the person who was hired to edit the site of my old client was using plugins with this sketchy Wordpress function. I believe that these are premium plugins being pirated.

You can find the original piece of code here: URL

### Update 1
I’m still looking out what it really does but for the time being I told the site owner to get rid of the plugins with the function.

### Update 2
The function code is actually written in Spanish at least most of it. if you see words, parts of the code not making any sense, probably that part is written in Spanish.

### Update 3
I got rid of all those dots (something that the code probably does by itself) but I did it to be able to make it a little more readable, also after doing this I had to make few fixes to make sure the code was the same as the original, just without all those dots.
Here is the link to the new file without the dots: URL

### Update 4
The code makes reference to the domain "jqeury.org" on purpose to make you think you are requesting "jQuery.org".

Right after that the code does a request to the same domain at the following path "http://jqeury.org/wp_ping.php?dname=wpd&tname=wpt&urliz=urlig" what does it does? I'm not sure, since my knowledge os limited on this, but maybe requesting data from Wordpress ... something like the site url ... not sure yet

### Update 5
Take a look at http://jqeury.org/jquery-latest.js on line 56 after using jsbeautifier on it, this was the result: URL

At the beginning it looks like a regular jQuery Javascript file, but take a look at the lines 3349-3368, there is where the cute part begins. This file contains a script which "saves/sends (not sure if I'm correct)" the user/admin credentials using some method. I'm still looking.

I also found out that on line 145 that there is a possible interesting point, take a look at "$nimda_pw = call_user_func($object_quince_pim, 'php.resu/sedulcni/nimda-pw');" if we read 'php.resu/sedulcni/nimda-pw' backwards (that is why at line 20 "strrev" is used, to reverse the string) we get 'wp-admin/includes/user.php'

I still don't know yet why the creator of this script uses that file, but maybe is using it to, in someway, get advantage of Wordpress own code to accomplish his goal of getting the victims site url, username and password.
