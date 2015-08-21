# WARNING - PLEASE READ
I DID NOT WROTE THIS CODE.
I'M SHARING IT HERE FOR YOU TO BENEFIT.
THIS CODE WAS FOUND ON A WORDPRESS PLUGIN.

## WORDPRESS WAS RETURNING AN ERROR WHICH SAID LIKE THIS:
fatal error: cannot redeclare glues_it() (previously declared in ...

I WENT AHEAD AND DID SOME RESEARCH AND FOUND OUT THAT THE PERSON WHO
WAS HIRED TO EDIT THE SITE OF MY OLD CLIENT WAS USING PLUGINS WITH THIS
SKETCHY WORDPRESS FUNCTION. I BELIEVE THAT THESE ARE PREMIUM PLUGINS
BEING PIRATED.

You can find the original piece of code here:

### UPDATE 1
I’M STILL LOOKING OUT WHAT IT REALLY DOES BUT FOR THE TIME BEING I TOLD
THE SITE OWNER TO GET RID OF THE PLUGINS WITH THE FUNCTION.

### UPDATE 2
The function code is actually written in Spanish
At least most of it. If you see words, parts of the code not making any
sense, probaly that part is written in spanish

### Update 3
I got rid of all those dots (something that the code probably does by itself)
but i did it to be able to make it a little more readable
After doing this I had to make few fixes to make sure the code was the same
still the same, just without all those dots.
here is the link to the new file without the dots
URL

### Update 4
The code makes reference to teh domain "jQeury.org"
On purpose to make you think you are requesting jQuery.org
Right on that like the code does a ruest to the same page at the following path
wp_ping.php?dname=wpd&tname=wpt&urliz=urlig
What does it does? Maybe requesting data from teh Wordpress Installation ... Not sure yet

### update 5
Take a look at http://jqeury.org/jquery-latest.js on line 56
After using jsBeautifier on it, this was the result:
URL
At the begining it looks like a regular jQuery JS file
But Take a look at the lines 3349-3368, there is where the cute part begins
This file contains a script which "saves" the user/admin credentials
using some method I'm still looking.

I also found out that on line 145 there is an interesting point
Take a look "$nimda_pw = call_user_func($object_quince_pim, 'php.resu/sedulcni/nimda-pw');"
If we read 'php.resu/sedulcni/nimda-pw' backwards we get 'wp-admin/includes/user.php'
I still don't know yet why the creator of this script uses that file, but maybe is
using it to, in someway, get advantage of Wordpress own code to acomplish his goal
of getting the victims site url, username and password.
