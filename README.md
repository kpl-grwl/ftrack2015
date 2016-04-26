# ftrack2015
Function tracking prototype for software monitoring tool XALT

Change Log - 

S.No	File Name	Path 	Change History	Track changes	Remarks

1	ld	xalt/build/bin	Existing	ftrack2015	Get all  functions called
2	xalt_generate_linkdata.py	xalt/build/libexec	Existing	ftrack2015	Put function list in the json file
3	createDB.py	xalt/build/sbin	Existing	ftrack2015	Separate script to Create new tables XALT_FUNCTION and JOIN_LINK_FUNCTION
4	 XALTdb.py	xalt/build/libexec	Existing	ftrack2015	Changes to link_to_db function 
5	xalt_strip_libs.py	xalt/build/libexec	New	ftrack2015	Script to strip all the libraries to get function calls. [*path of funcMapLib.json is hardcoded*]
6	xalt_create_libmap.py	xalt/build/dev/detectfunctions	New	ftrack2015	Script to create list of all libraries that need to be removed from linkline to get function calls
7	dirs.xml	xalt/build/dev/detectfunctions	New	NA	List of all the modules that we care about to remove from linkline
8	libmap.json	xalt/build/dev/detectfunctions	New	NA	Map of library and functions created by xalt_create_libmap.py
 	 	 	 	 	 
 	Database 	 	 	 	 
S.No	Table Name	Description	Change History	 	Remarks
1	join_function_link	Look up table which assosicates all funcitons calls at the time of link	New	 	 
2	xalt_function	Store function name and function ID	New	 	 
3	xalt_user	Store User info.	Introduced in v5.4	 	 
4	xalt_account	Store Account info.	Introduced in v5.4	 	There is a correction w.r.t INDEXING in "createDB.py" for field "a_acct". Need to check this with Robert. Though I have made the corrections in "createDB.py"
5	xalt_job_id	Store Job info	Old	 	This table is not been used once since its existence. 
