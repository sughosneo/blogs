### Profiling/Introspecting - Python Code

It's always interesting to look into the performance of our own written code. When we write any 
specific functions we don't think much either about the performance in terms of time consumptions or 
memory usage. But sometimes, it's actually important to review the code in details and look into execution 
internally.      

There are many libraries available in python language which helps developer to profile any code execution.
 
Let's see how it happens ? To see the implementation here is the github reference - https://github.com/sughosneo/pythonprofiling

1. There are 50000 names are present in one of the file FirstNameList.json
2. And in another file SecondNameList.json we have less names. 

##### In this <<Duplicate.py>> file - we do compare each name with another name in second list. 
##### Complexity is  - O(n*n)
        
        def __isDuplicate(self,name,secondNameList):

            isDuplicate = False
    
            for eachName in secondNameList:
                if eachName == name:
                    isDuplicate=True
                    break
    
            return isDuplicate

        @timeStatsProfiler
        @memoryProfile
        def getDuplicateItems(self,firstNameList,secondNameList):
    
            duplicateItemList = []
    
            for eachName in firstNameList:
                if self.__isDuplicate(eachName,secondNameList):
                    duplicateItemList.append(eachName)
    
            print(duplicateItemList)
            
        # So when we look into the performance both from time or memory point of view.
        
        Line #    Mem usage    Increment   Line Contents
        ================================================
            19     16.5 MiB     16.5 MiB       @timeStatsProfiler
            20                                 @memoryProfile
            21                                 def getDuplicateItems(self,firstNameList,secondNameList):
            22                             
            23     16.5 MiB      0.0 MiB           duplicateItemList = []
            24                             
            25     16.5 MiB      0.0 MiB           for eachName in firstNameList:
            26     16.5 MiB      0.0 MiB               if self.__isDuplicate(eachName,secondNameList):
            27     16.5 MiB      0.0 MiB                   duplicateItemList.append(eachName)
            28                             
            29     16.5 MiB      0.0 MiB           print(duplicateItemList)
        
        
                 77632 function calls (76760 primitive calls) in 26.634 seconds
        
           Random listing order was used
        
           ncalls  tottime  percall  cumtime  percall filename:lineno(function)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\codecs.py:259(__init__)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\codecs.py:308(__init__)
                2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\codecs.py:318(decode)
              111    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\ntpath.py:43(normcase)
              221    0.001    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\ntpath.py:121(splitdrive)
              221    0.002    0.000    0.004    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\ntpath.py:471(normpath)
              221    0.000    0.000    0.005    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\ntpath.py:538(abspath)
              107    0.000    0.000    0.007    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\genericpath.py:16(exists)
                1    4.364    4.364   26.603   26.603 D:/projects/pythonprofiling/Duplicate.py:19(getDuplicateItems)
            50000   22.237    0.000   22.237    0.000 D:/projects/pythonprofiling/Duplicate.py:8(__isDuplicate)
               52    0.000    0.000    0.015    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\re.py:231(compile)
               52    0.000    0.000    0.015    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\re.py:286(_compile)
             1432    0.001    0.000    0.002    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\enum.py:265(__call__)
            276/2    0.002    0.000    0.007    0.003 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:64(_compile)
             1432    0.001    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\enum.py:515(__new__)
               62    0.000    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:223(_compile_charset)
               62    0.000    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:250(_optimize_charset)
               48    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\enum.py:791(__or__)
              668    0.001    0.000    0.003    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\enum.py:797(__and__)
                9    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:376(_mk_bitmap)
                9    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:378(<listcomp>)
               67    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:388(_simple)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:414(_get_literal_prefix)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:441(_get_charset_prefix)
                2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:482(_compile_info)
                4    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:539(isstring)
                2    0.000    0.000    0.007    0.003 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:542(_code)
                2    0.000    0.000    0.015    0.007 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:557(compile)
                2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:76(__init__)
               59    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:81(groups)
               27    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:84(opengroup)
               27    0.000    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:96(closegroup)
              276    0.001    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:111(__init__)
              272    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:159(__len__)
             1023    0.001    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:163(__getitem__)
               67    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:167(__setitem__)
              393    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:171(append)
           370/97    0.001    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:173(getwidth)
                2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:223(__init__)
              894    0.001    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:232(__next)
              508    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:248(match)
              647    0.000    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:253(get)
              224    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:285(tell)
               13    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:294(_class_escape)
               32    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:342(_escape)
             53/2    0.000    0.000    0.008    0.004 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:407(_parse_sub)
            186/5    0.002    0.000    0.008    0.002 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:469(_parse)
                2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:829(fix_flags)
                2    0.000    0.000    0.008    0.004 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:845(parse)
               11    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:56(unicode)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:558(__init__)
                1    0.000    0.000    0.031    0.031 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:563(add)
               12    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:608(<genexpr>)
                2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:602(items)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:615(__init__)
                1    0.000    0.000    0.031    0.031 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:626(__call__)
                1    0.000    0.000    0.031    0.031 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:641(add_function)
                1    0.000    0.000   26.603   26.603 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:657(f)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:653(wrap_function)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:676(enable_by_count)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:683(disable_by_count)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:743(enable)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:750(disable)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:754(show_results)
                1    0.000    0.000   26.634   26.634 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:1071(wrapper)
                4    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:1099(<genexpr>)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:1087(choose_backend)
              266    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:63(ismodule)
                2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:72(isclass)
                2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:80(ismethod)
                2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:158(isfunction)
                2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:228(istraceback)
                2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:238(isframe)
                3    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:252(iscode)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:475(_is_wrapper)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:458(unwrap)
              116    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:613(getfile)
              333    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:657(<genexpr>)
              332    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:660(<genexpr>)
              111    0.000    0.000    0.008    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:650(getsourcefile)
              111    0.000    0.000    0.012    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:672(getabsfile)
                1    0.000    0.000    0.015    0.015 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:684(getmodule)
                1    0.000    0.000    0.016    0.016 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:730(findsource)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:852(__init__)
               64    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:861(tokeneater)
                1    0.000    0.000    0.014    0.014 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:905(getblock)
                1    0.000    0.000    0.030    0.030 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:916(getsourcelines)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\linecache.py:53(checkcache)
                2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\linecache.py:37(getlines)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\linecache.py:82(updatecache)
               51    0.000    0.000    0.013    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\tokenize.py:152(_compile)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\tokenize.py:379(read_or_stop)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\tokenize.py:385(find_cookie)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\tokenize.py:355(detect_encoding)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\tokenize.py:448(open)
               65    0.000    0.000    0.014    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\tokenize.py:492(_tokenize)
                1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\tokenize.py:729(generate_tokens)
               64    0.000    0.000    0.000    0.000 <string>:12(__new__)
                2    0.000    0.000    0.000    0.000 {built-in method _codecs.utf_8_decode}
                1    0.000    0.000    0.000    0.000 {method 'disable' of '_lsprof.Profiler' objects}
               54    0.000    0.000    0.000    0.000 {method 'match' of '_sre.SRE_Pattern' objects}
               51    0.000    0.000    0.000    0.000 {method 'span' of '_sre.SRE_Match' objects}
                2    0.000    0.000    0.000    0.000 {built-in method _sre.compile}
              108    0.007    0.000    0.007    0.000 {built-in method nt.stat}
              221    0.000    0.000    0.000    0.000 {built-in method nt._getfullpathname}
              774    0.000    0.000    0.000    0.000 {built-in method nt.fspath}
                1    0.000    0.000    0.000    0.000 {method 'readline' of '_io.BufferedReader' objects}
                1    0.000    0.000    0.000    0.000 {method 'seek' of '_io.BufferedReader' objects}
                1    0.000    0.000    0.000    0.000 {method 'readlines' of '_io._IOBase' objects}
               15    0.000    0.000    0.000    0.000 {method 'write' of '_io.TextIOWrapper' objects}
                1    0.000    0.000    0.000    0.000 {built-in method io.open}
              214    0.000    0.000    0.000    0.000 {method 'find' of 'bytearray' objects}
                9    0.000    0.000    0.000    0.000 {method 'translate' of 'bytearray' objects}
                1    0.000    0.000    0.000    0.000 {method 'decode' of 'bytes' objects}
                1    0.000    0.000    0.000    0.000 {method 'startswith' of 'bytes' objects}
              197    0.000    0.000    0.000    0.000 {method 'get' of 'dict' objects}
                3    0.000    0.000    0.000    0.000 {method 'items' of 'dict' objects}
                1    0.000    0.000    0.000    0.000 {method 'update' of 'dict' objects}
             3201    0.000    0.000    0.000    0.000 {method 'append' of 'list' objects}
                1    0.000    0.000    0.000    0.000 {method 'insert' of 'list' objects}
               10    0.000    0.000    0.000    0.000 {method 'extend' of 'list' objects}
                1    0.000    0.000    0.000    0.000 {method 'pop' of 'list' objects}
               64    0.000    0.000    0.000    0.000 {built-in method __new__ of type object at 0x5DBB9CA8}
              553    0.000    0.000    0.000    0.000 {method 'replace' of 'str' objects}
              221    0.000    0.000    0.000    0.000 {method 'split' of 'str' objects}
              221    0.000    0.000    0.000    0.000 {method 'join' of 'str' objects}
              111    0.000    0.000    0.000    0.000 {method 'lower' of 'str' objects}
              221    0.000    0.000    0.000    0.000 {method 'lstrip' of 'str' objects}
              443    0.000    0.000    0.000    0.000 {method 'startswith' of 'str' objects}
              445    0.000    0.000    0.000    0.000 {method 'endswith' of 'str' objects}
               43    0.000    0.000    0.000    0.000 {method 'isidentifier' of 'str' objects}
               25    0.000    0.000    0.000    0.000 {method 'format' of 'str' objects}
              222    0.000    0.000    0.001    0.000 {built-in method builtins.any}
                1    0.000    0.000    0.000    0.000 {built-in method builtins.getattr}
              265    0.000    0.000    0.000    0.000 {built-in method builtins.hasattr}
                1    0.000    0.000    0.000    0.000 {built-in method builtins.id}
             2581    0.001    0.000    0.001    0.000 {built-in method builtins.isinstance}
                1    0.000    0.000    0.000    0.000 {built-in method builtins.iter}
        4385/4292    0.001    0.000    0.001    0.000 {built-in method builtins.len}
              156    0.000    0.000    0.000    0.000 {built-in method builtins.max}
              709    0.000    0.000    0.000    0.000 {built-in method builtins.min}
              358    0.000    0.000    0.000    0.000 {built-in method builtins.ord}
                1    0.001    0.001    0.001    0.001 {built-in method builtins.print}
                2    0.000    0.000    0.000    0.000 {built-in method sys.settrace}
                1    0.000    0.000    0.000    0.000 {built-in method sys.gettrace}
        
        
        # Memory usage would be 16 MB and the total time took - 26.634 seconds
        

##### In this <<DuplicateUpdated.py>> file - we make a hashmap and then we check for the dupliacte for each name in SecondNameList file.
##### Complexity comes down to - O(n)

            def __isDuplicate(self, name, firstNameListDict):

                isDuplicate = False
        
                if firstNameListDict and \
                        name in firstNameListDict:
                    isDuplicate = True
        
                return isDuplicate
        
            @timeStatsProfiler
            @memoryProfile
            def getDuplicateItems(self, firstNameList, secondNameList):
        
                firstNameListDict = {}
                duplicateItemList = []
        
                # Populate firstName list dict
                for eachName in firstNameList:
                    firstNameListDict[eachName] = 1
        
                for eachName in secondNameList:
        
                    if self.__isDuplicate(eachName, firstNameListDict):
                        duplicateItemList.append(eachName)
        
                print(duplicateItemList)
            
            
            # In the second file we changed out the duplicate function logic and it updated performance looks like.
            
            Line #    Mem usage    Increment   Line Contents
            ================================================
                18     16.7 MiB     16.7 MiB       @timeStatsProfiler
                19                                 @memoryProfile
                20                                 def getDuplicateItems(self, firstNameList, secondNameList):
                21                             
                22     16.7 MiB      0.0 MiB           firstNameListDict = {}
                23     16.7 MiB      0.0 MiB           duplicateItemList = []
                24                             
                25                                     # Populate firstName list dict
                26     17.8 MiB      0.0 MiB           for eachName in firstNameList:
                27     17.8 MiB      0.8 MiB               firstNameListDict[eachName] = 1
                28                             
                29     17.8 MiB      0.0 MiB           for eachName in secondNameList:
                30                             
                31     17.8 MiB      0.0 MiB               if self.__isDuplicate(eachName, firstNameListDict):
                32     17.8 MiB      0.0 MiB                   duplicateItemList.append(eachName)
                33                             
                34     17.8 MiB      0.0 MiB           print(duplicateItemList)
            
            
                     28078 function calls (27206 primitive calls) in 4.864 seconds
            
               Random listing order was used
            
               ncalls  tottime  percall  cumtime  percall filename:lineno(function)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\codecs.py:259(__init__)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\codecs.py:308(__init__)
                    2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\codecs.py:318(decode)
                  111    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\ntpath.py:43(normcase)
                  221    0.001    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\ntpath.py:121(splitdrive)
                  221    0.002    0.000    0.004    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\ntpath.py:471(normpath)
                  221    0.000    0.000    0.004    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\ntpath.py:538(abspath)
                  107    0.000    0.000    0.007    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\genericpath.py:16(exists)
                    1    4.828    4.828    4.836    4.836 D:/projects/pythonprofiling/DuplicateUpdated.py:18(getDuplicateItems)
                  265    0.002    0.000    0.002    0.000 D:/projects/pythonprofiling/DuplicateUpdated.py:8(__isDuplicate)
                   70    0.000    0.000    0.012    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\re.py:231(compile)
                   70    0.000    0.000    0.012    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\re.py:286(_compile)
                 1432    0.001    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\enum.py:265(__call__)
                276/2    0.001    0.000    0.006    0.003 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:64(_compile)
                 1432    0.001    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\enum.py:515(__new__)
                   62    0.000    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:223(_compile_charset)
                   62    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:250(_optimize_charset)
                   48    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\enum.py:791(__or__)
                  668    0.001    0.000    0.003    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\enum.py:797(__and__)
                    9    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:376(_mk_bitmap)
                    9    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:378(<listcomp>)
                   67    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:388(_simple)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:414(_get_literal_prefix)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:441(_get_charset_prefix)
                    2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:482(_compile_info)
                    4    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:539(isstring)
                    2    0.000    0.000    0.006    0.003 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:542(_code)
                    2    0.000    0.000    0.012    0.006 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_compile.py:557(compile)
                    2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:76(__init__)
                   59    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:81(groups)
                   27    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:84(opengroup)
                   27    0.000    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:96(closegroup)
                  276    0.001    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:111(__init__)
                  272    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:159(__len__)
                 1023    0.000    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:163(__getitem__)
                   67    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:167(__setitem__)
                  393    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:171(append)
               370/97    0.001    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:173(getwidth)
                    2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:223(__init__)
                  894    0.001    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:232(__next)
                  508    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:248(match)
                  647    0.000    0.000    0.001    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:253(get)
                  224    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:285(tell)
                   13    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:294(_class_escape)
                   32    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:342(_escape)
                 53/2    0.000    0.000    0.007    0.003 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:407(_parse_sub)
                186/5    0.002    0.000    0.006    0.001 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:469(_parse)
                    2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:829(fix_flags)
                    2    0.000    0.000    0.007    0.003 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\sre_parse.py:845(parse)
                   17    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:56(unicode)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:558(__init__)
                    1    0.000    0.000    0.027    0.027 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:563(add)
                   18    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:608(<genexpr>)
                    2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:602(items)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:615(__init__)
                    1    0.000    0.000    0.027    0.027 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:626(__call__)
                    1    0.000    0.000    0.027    0.027 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:641(add_function)
                    1    0.000    0.000    4.836    4.836 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:657(f)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:653(wrap_function)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:676(enable_by_count)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:683(disable_by_count)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:743(enable)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:750(disable)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:754(show_results)
                    1    0.000    0.000    4.864    4.864 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:1071(wrapper)
                    4    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:1099(<genexpr>)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\site-packages\memory_profiler.py:1087(choose_backend)
                  266    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:63(ismodule)
                    2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:72(isclass)
                    2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:80(ismethod)
                    2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:158(isfunction)
                    2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:228(istraceback)
                    2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:238(isframe)
                    4    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:252(iscode)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:475(_is_wrapper)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:458(unwrap)
                  116    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:613(getfile)
                  333    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:657(<genexpr>)
                  332    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:660(<genexpr>)
                  111    0.000    0.000    0.008    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:650(getsourcefile)
                  111    0.000    0.000    0.011    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:672(getabsfile)
                    1    0.001    0.001    0.014    0.014 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:684(getmodule)
                    1    0.000    0.000    0.015    0.015 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:730(findsource)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:852(__init__)
                   87    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:861(tokeneater)
                    1    0.000    0.000    0.012    0.012 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:905(getblock)
                    1    0.000    0.000    0.027    0.027 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\inspect.py:916(getsourcelines)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\linecache.py:53(checkcache)
                    2    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\linecache.py:37(getlines)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\linecache.py:82(updatecache)
                   69    0.000    0.000    0.012    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\tokenize.py:152(_compile)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\tokenize.py:379(read_or_stop)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\tokenize.py:385(find_cookie)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\tokenize.py:355(detect_encoding)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\tokenize.py:448(open)
                   88    0.000    0.000    0.012    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\tokenize.py:492(_tokenize)
                    1    0.000    0.000    0.000    0.000 C:\Users\sugho\AppData\Local\Programs\Python\Python36-32\lib\tokenize.py:729(generate_tokens)
                   87    0.000    0.000    0.000    0.000 <string>:12(__new__)
                    2    0.000    0.000    0.000    0.000 {built-in method _codecs.utf_8_decode}
                    1    0.000    0.000    0.000    0.000 {method 'disable' of '_lsprof.Profiler' objects}
                   72    0.000    0.000    0.000    0.000 {method 'match' of '_sre.SRE_Pattern' objects}
                   69    0.000    0.000    0.000    0.000 {method 'span' of '_sre.SRE_Match' objects}
                    2    0.000    0.000    0.000    0.000 {built-in method _sre.compile}
                  108    0.007    0.000    0.007    0.000 {built-in method nt.stat}
                  221    0.000    0.000    0.000    0.000 {built-in method nt._getfullpathname}
                  774    0.000    0.000    0.000    0.000 {built-in method nt.fspath}
                    1    0.000    0.000    0.000    0.000 {method 'readline' of '_io.BufferedReader' objects}
                    1    0.000    0.000    0.000    0.000 {method 'seek' of '_io.BufferedReader' objects}
                    1    0.000    0.000    0.000    0.000 {method 'readlines' of '_io._IOBase' objects}
                   21    0.000    0.000    0.000    0.000 {method 'write' of '_io.TextIOWrapper' objects}
                    1    0.000    0.000    0.000    0.000 {built-in method io.open}
                  214    0.000    0.000    0.000    0.000 {method 'find' of 'bytearray' objects}
                    9    0.000    0.000    0.000    0.000 {method 'translate' of 'bytearray' objects}
                    1    0.000    0.000    0.000    0.000 {method 'decode' of 'bytes' objects}
                    1    0.000    0.000    0.000    0.000 {method 'startswith' of 'bytes' objects}
                  203    0.000    0.000    0.000    0.000 {method 'get' of 'dict' objects}
                    3    0.000    0.000    0.000    0.000 {method 'items' of 'dict' objects}
                    1    0.000    0.000    0.000    0.000 {method 'update' of 'dict' objects}
                 3138    0.000    0.000    0.000    0.000 {method 'append' of 'list' objects}
                    1    0.000    0.000    0.000    0.000 {method 'insert' of 'list' objects}
                   10    0.000    0.000    0.000    0.000 {method 'extend' of 'list' objects}
                    1    0.000    0.000    0.000    0.000 {method 'pop' of 'list' objects}
                   87    0.000    0.000    0.000    0.000 {built-in method __new__ of type object at 0x5DBB9CA8}
                  553    0.000    0.000    0.000    0.000 {method 'replace' of 'str' objects}
                  221    0.000    0.000    0.000    0.000 {method 'split' of 'str' objects}
                  221    0.000    0.000    0.000    0.000 {method 'join' of 'str' objects}
                  111    0.000    0.000    0.000    0.000 {method 'lower' of 'str' objects}
                  221    0.000    0.000    0.000    0.000 {method 'lstrip' of 'str' objects}
                    1    0.000    0.000    0.000    0.000 {method 'rstrip' of 'str' objects}
                  443    0.000    0.000    0.000    0.000 {method 'startswith' of 'str' objects}
                  445    0.000    0.000    0.000    0.000 {method 'endswith' of 'str' objects}
                   57    0.000    0.000    0.000    0.000 {method 'isidentifier' of 'str' objects}
                   37    0.000    0.000    0.000    0.000 {method 'format' of 'str' objects}
                  222    0.000    0.000    0.000    0.000 {built-in method builtins.any}
                    1    0.000    0.000    0.000    0.000 {built-in method builtins.getattr}
                  265    0.000    0.000    0.000    0.000 {built-in method builtins.hasattr}
                    1    0.000    0.000    0.000    0.000 {built-in method builtins.id}
                 2582    0.001    0.000    0.001    0.000 {built-in method builtins.isinstance}
                    1    0.000    0.000    0.000    0.000 {built-in method builtins.iter}
            4394/4301    0.001    0.000    0.001    0.000 {built-in method builtins.len}
                  156    0.000    0.000    0.000    0.000 {built-in method builtins.max}
                  709    0.000    0.000    0.000    0.000 {built-in method builtins.min}
                  358    0.000    0.000    0.000    0.000 {built-in method builtins.ord}
                    1    0.005    0.005    0.005    0.005 {built-in method builtins.print}
                    2    0.000    0.000    0.000    0.000 {built-in method sys.settrace}
                    1    0.000    0.000    0.000    0.000 {built-in method sys.gettrace}

            
           # Though the memory usage is same but the time stats and consumption has reduced down to - in 4.864 seconds

##### Note :
If someone is using professional edition of pycharm then can use the cProfiling inbuilt module and look into the performance.   
https://www.jetbrains.com/help/pycharm/profiler.html 
 
