#START-FILE-LIST
# File List auto generated by waf2cmake.py, do not modify manually.

start_sources()
# -- cryxml.waf_files --
sources_platform(ALL)
add_sources("CryXML_uber_0.cpp"
	SOURCE_GROUP "Source Files"
		"CryXML.cpp"
		"XMLSerializer.cpp"
		"ICryXML.h"
		"IXMLSerializer.h"
		"XMLSerializer.h"
	SOURCE_GROUP "Source Files\\\\XML"
		"XML/xml.cpp"
		"XML/xml.h"
)

add_sources("NoUberFile"
	SOURCE_GROUP "Source Files"
		"stdafx.h"
		"stdafx.cpp"
		"CryXML.def"
)

end_sources()
#END-FILE-LIST

CryResourceCompilerModule(CryXML PCH "StdAfx.cpp" SOLUTION_FOLDER "RC")
target_include_directories(${THIS_PROJECT} PRIVATE 
	${CRYENGINE_SOURCE_DIR}/Code/Tools/CryCommonTools 
	${CRYENGINE_SOURCE_DIR}/Code/Tools 
	${CMAKE_SOURCE_DIR}/ResourceCompiler)
target_compile_definitions(${THIS_PROJECT} PRIVATE -DCRYXML_EXPORTS -DCRYTOOLS)
target_link_libraries(${THIS_PROJECT} PRIVATE expat)

