#Gradle error after importing projects from eclipse

I know this is a old post. But instead of deleting .gradle directory, you just need to delete registry.bin.lock. You will find this in the same directory where registry.bin is. This will save a lot of your time.

Thanks

Delete the file mentioned above and try again. ===> Fixed.