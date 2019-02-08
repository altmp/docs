# Script

> REQUEST_SCRIPT - 0x6EB5F71AA68F2E8E 0xE26B2666

void REQUEST_SCRIPT(char* scriptName)

```
For a full list, see here: pastebin.com/yLNWicUi
```

> SET_SCRIPT_AS_NO_LONGER_NEEDED - 0xC90D2DCACD56184C 0x6FCB7795

void SET_SCRIPT_AS_NO_LONGER_NEEDED(char* scriptName)

```
For a full list, see here: pastebin.com/yLNWicUi
```

> HAS_SCRIPT_LOADED - 0xE6CC9F3BA0FB9EF1 0x5D67F751

BOOL HAS_SCRIPT_LOADED(char* scriptName)

```
Returns if a script has been loaded into the game. Used to see if a script was loaded after requesting.

For a full list, see here: pastebin.com/yLNWicUi
```

> DOES_SCRIPT_EXIST - 0xFC04745FBE67C19A 0xDEAB87AB

BOOL DOES_SCRIPT_EXIST(char* scriptName)

```
For a full list, see here: pastebin.com/yLNWicUi
```

> _REQUEST_STREAMED_SCRIPT - 0xD62A67D26D9653E6 0x1C68D9DC

void _REQUEST_STREAMED_SCRIPT(Hash scriptHash)

```
formerly _REQUEST_STREAMED_SCRIPT
```

> _SET_STREAMED_SCRIPT_AS_NO_LONGER_NEEDED - 0xC5BC038960E9DB27 0x96C26F66

void _SET_STREAMED_SCRIPT_AS_NO_LONGER_NEEDED(Hash scriptHash)



> _HAS_STREAMED_SCRIPT_LOADED - 0x5F0F0C783EB16C04 0x06674818

BOOL _HAS_STREAMED_SCRIPT_LOADED(Hash scriptHash)



> _IS_STREAMED_SCRIPT_RUNNING - 0xF86AA3C56BA31381 

BOOL _IS_STREAMED_SCRIPT_RUNNING(Hash scriptHash)

```
formerly _IS_STREAMED_SCRIPT_RUNNING

Jenkins hash: 0x19EAE282
```

> TERMINATE_THREAD - 0xC8B189ED9138BCD4 0x253FD520

void TERMINATE_THREAD(int threadId)



> IS_THREAD_ACTIVE - 0x46E9AE36D8FA6417 0x78D7A5A0

BOOL IS_THREAD_ACTIVE(int threadId)



> _GET_THREAD_NAME - 0x05A42BA9FC8DA96B 0xBE7ACD89

char* _GET_THREAD_NAME(int threadId)

```
The reversed code looks like this (Sasuke78200)

//
char g_szScriptName[64];

char* _0xBE7ACD89(int a_iThreadID)
{
	scrThread* l_pThread;
	
	// Get the script thread
	l_pThread = GetThreadByID(a_iThreadID);	
	
	if(l_pThread == 0 || l_pThread-&gt;m_iThreadState == 2)
	{
		strncpy(g_szScriptName, '', 64);
	}
	else
	{
		strncpy(g_szScriptName, l_pThread-&gt;m_szScriptName, 64);
	}	
	
	return g_szScriptName;
}
```

> _BEGIN_ENUMERATING_SCRIPTS - 0xDADFADA5A20143A8 0xBB4E2F66

void _BEGIN_ENUMERATING_SCRIPTS()

```
MulleDK19: Starts a new enumeration of the current threads.
Call this first, then _GET_ID_OF_NEXT_THREAD_IN_ENUMERATION (0x30B4FA1C82DD4B9F)

-----------------------------------------------------------------------
Some other guy: See _GET_ID_OF_NEXT_THREAD_IN_ENUMERATION (0x30B4FA1C82DD4B9F) for an example
```

> _GET_ID_OF_NEXT_SCRIPT_IN_ENUMERATION - 0x30B4FA1C82DD4B9F 0x1E28B28F

int _GET_ID_OF_NEXT_SCRIPT_IN_ENUMERATION()

```
MulleDK19: Gets the ID of the next active thread.
First call _BEGIN_ENUMERATE_THREADS (0xDADFADA5A20143A8).
Any subsequent call to this function will then return the ID of the next active thread.

If the function returns 0, the end of the enumeration has been reached.

-----------------------------------------------------------------------
Some other guy: Here's an example:

	std::vector&lt;int&gt; vecCurrentThreads;
	void update_current_threads_list()
	{
		vecCurrentThreads.clear();
		
		_BEGIN_ENUMERATING_THREADS();
		int id = _GET_ID_OF_NEXT_THREAD_IN_ENUMERATION();
		
		while (id != 0)
		{
			id = _GET_ID_OF_NEXT_THREAD_IN_ENUMERATION();
			vecCurrentThreads.push_back(id);
		}
	}
```

> GET_ID_OF_THIS_THREAD - 0xC30338E8088E2E21 0xDE524830

int GET_ID_OF_THIS_THREAD()



> TERMINATE_THIS_THREAD - 0x1090044AD1DA76FA 0x3CD9CBB7

void TERMINATE_THIS_THREAD()



> _GET_NUMBER_OF_INSTANCES_OF_STREAMED_SCRIPT - 0x2C83A9DA6BFFC4F9 0x029D3841

int _GET_NUMBER_OF_INSTANCES_OF_STREAMED_SCRIPT(Hash scriptHash)

```
Gets the number of instances of the specified script is currently running.

Actually returns numInstances - 1.
if (scriptPtr)
    v3 = GetNumberOfInstancesOfScript(scriptPtr) - 1;
return v3;
```

> GET_THIS_SCRIPT_NAME - 0x442E0A7EDE4A738A 0xA40FD5D9

char* GET_THIS_SCRIPT_NAME()



> _GET_THIS_SCRIPT_HASH - 0x8A1C8B1738FFE87E 0x2BEE1F45

Hash _GET_THIS_SCRIPT_HASH()



> GET_NUMBER_OF_EVENTS - 0x5F92A689A06620AA 0xA3525D60

int GET_NUMBER_OF_EVENTS(int p0)



> GET_EVENT_EXISTS - 0x936E6168A9BCEDB5 0xA1B447B5

BOOL GET_EVENT_EXISTS(int p0, int eventIndex)



> GET_EVENT_AT_INDEX - 0xD8F66A3A60C62153 0xB49C1442

int GET_EVENT_AT_INDEX(int p0, int eventIndex)



> GET_EVENT_DATA - 0x2902843FCD2B2D79 0x4280F92F

BOOL GET_EVENT_DATA(int p0, int eventIndex, int* eventData, int p3)



> TRIGGER_SCRIPT_EVENT - 0x5AE99C571D5BBE5D 0x54763B35

void TRIGGER_SCRIPT_EVENT(int p0, Vector3* argsStruct, int argsStructSize, int bitset)



> SHUTDOWN_LOADING_SCREEN - 0x078EBE9809CCD637 0xA2826D17

void SHUTDOWN_LOADING_SCREEN()



> SET_NO_LOADING_SCREEN - 0x5262CC1995D07E09 0xC8055034

void SET_NO_LOADING_SCREEN(BOOL toggle)



> _GET_NO_LOADING_SCREEN - 0x18C1270EA7F199BC 

BOOL _GET_NO_LOADING_SCREEN()



> 0xB1577667C3708F9B 0xB03BCCDF

void 0xB1577667C3708F9B()



