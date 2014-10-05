###print_r to error_log
	 public function er($data)
    {
        ob_start();
        print_r($data);
        $contents = ob_get_contents();
        ob_end_clean();
        error_log($contents);
    }
###rewrite git commit time
	git filter-branch --env-filter \
    'if [ $GIT_COMMIT = d7e28f6bd2f4b0caa37d9b0b1123ad6c06a36d6c ]
     then
         export GIT_AUTHOR_DATE="Sat Sep 28 19:25:22 2014 -0800"
         export GIT_COMMITTER_DATE="Sat Sep 28  19:25:22 2014 -0800"
     fi'
### show directory sizes
	du -sh dir/ 
### python environment directories
	print("Path at terminal when executing this file")
	print(os.getcwd() + "\n")
	
	print("This file path, relative to os.getcwd()")
	print(__file__ + "\n")
	
	print("This file full path (following symlinks)")
	full_path = os.path.realpath(__file__)
	print(full_path + "\n")
	
	print("This file directory and name")
	path, file = os.path.split(full_path)
	print(path + ' --> ' + file + "\n")
	
	print("This file directory only")
	print(os.path.dirname(full_path))