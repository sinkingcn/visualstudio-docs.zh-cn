---
title: 格式说明符在调试器中 （c + +） |Microsoft Docs
ms.custom: ''
ms.date: 11/20/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- QuickWatch dialog box, format specifiers in C++
- variables [debugger], watch variable symbols
- symbols, watch variable formatting
- QuickWatch dialog box, using format specifiers
- expressions [C++], format specifiers
- specifiers, watch variable format
- specifiers
- Watch window, format specifiers in C++
- watch variable symbols
- format specifiers, debugger
- debugger, format specifiers recognized by
ms.assetid: 0f6f3b7c-ce2c-4b4d-b14f-7589dbed5444
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 73cd5655a5cb843c29fb628a2ec233860410dc7c
ms.sourcegitcommit: 81e9d90843ead658bc73b30c869f25921d99e116
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2018
ms.locfileid: "52305736"
---
# <a name="format-specifiers-for-c-in-the-visual-studio-debugger"></a>在 Visual Studio 调试器中的 c + + 格式说明符
你可以在其中一个值中显示的格式**监视**窗口是通过使用格式说明符。  
  
 此外可以使用中的格式说明符**即时**窗口中，**命令**窗口中，在[跟踪点](../debugger/using-breakpoints.md#BKMK_Print_to_the_Output_window_with_tracepoints)，并且即使在源窗口中。 如果暂停这些窗口中的表达式时，结果将出现在[数据提示](../debugger/view-data-values-in-data-tips-in-the-code-editor.md)。 “数据提示”显示格式说明符。  
  
> [!NOTE]
>  如果 Visual Studio 本机调试器更改为新的调试引擎中，添加了一些新的格式说明符和某些旧的已删除。 当你使用 C++/CLI 进行互操作（混合本机和托管）调试时，仍使用较早的调试器。 
  
## <a name="set-format-specifiers"></a>组格式说明符  
我们将使用下面的示例代码：  
  
```C++  
int main() {  
    int my_var1 = 0x0065;  
    int my_var2 = 0x0066;  
    int my_var3 = 0x0067;  
}  
```  
  
 添加`my_var1`变量**观看**调试时，窗口**调试** > **Windows** > **观看** > **观看 1**。 接下来，右键单击该变量，并选择**十六进制显示**。 现在**监视**窗口将显示值 0x0065。 若要查看此值表示为字符而不是一个整数，首先右键单击，然后取消选中**十六进制显示**。 然后添加字符格式说明符 **，c**中**名称**变量名之后的列。 **值**列现在显示**101 'e'**。  
  
 ![WatchFormatCPlus1](../debugger/media/watchformatcplus1.png "WatchFormatCPlus1")  
  
##  <a name="BKMK_Visual_Studio_2012_format_specifiers"></a>格式说明符  
 下表描述了可以使用 Visual Studio 中的格式说明符。 加粗的说明符仅支持为新的调试器，而不是针对互操作调试使用 C + + /cli CLI。  
  
|说明符|格式|原始监视值|显示的值|  
|---------------|------------|--------------------------|---------------------|  
|d|十进制整数|0x00000066|102|  
|o|无符号的八进制整数|0x00000066|000000000146|  
|x<br /><br /> **h**|十六进制整数|102|0xcccccccc|  
|X<br /><br /> **H**|十六进制整数|102|0xcccccccc|  
|c|单个字符|0x0065, c|101 'e'|  
|秒|const char * 字符串 （括在引号中）|\<位置 >"你好 world"|"hello world"|  
|**sb**|const char * 字符串（无引号）|\<位置 >"你好 world"|hello world|  
|s8|UTF-8 字符串|\<位置 >"这是 utf-8 咖啡杯 â˜•"|"这是 utf-8 咖啡杯 ☕"|
|**s8b**|UTF-8 字符串（无引号）|\<位置 >"你好 world"|hello world|  
|su|Unicode （utf-16 编码） 字符串 （括在引号中）|\<位置 > L"你好 world"|L"hello world"<br /><br /> u"hello world"|  
|sub|Unicode（UTF-16 编码）字符串（无引号）|\<位置 > L"你好 world"|hello world|  
|bstr|BSTR 二进制字符串 （括在引号中）|\<位置 > L"你好 world"|L"hello world"|  
|env|环境块（双空终止字符串）|\<位置 > L"=:: =::\\\\"|L"=:: =::\\\\\\0 = C: = C:\\\\windows\\\\system32\\0ALLUSERSPROFILE =...|
|**s32**|UTF-32 的字符串 （带有引号）|\<位置 > U"你好 world"|u"hello world"|  
|**s32b**|UTF-32 string (no quotation marks)|\<位置 > U"你好 world"|hello world|  
|**en**|enum|Saturday(6)|星期六|  
|**hv**|指针类型 - 指示被检查的指针值是数组的堆分配的结果，如 `new int[3]`。|\<location>{\<first member>}|\<位置 > {\<第一个成员 >，\<第二个成员 >，...}|  
|**na**|取消指向对象的指针的内存地址。|\<location>, {member=value...}|{member=value...}|  
|**nd**|仅显示基类信息，忽略派生的类|`(Shape*) square` 包括基类和派生类信息|仅显示基类信息|  
|hr|HRESULT 或 Win32 错误代码。 Hresult 为不再需要此说明符，因为调试器自动将它们进行解码。|S_OK|S_OK|  
|wc|窗口类标志|0x0010|WC_DEFAULTCHAR|  
|wm|Windows 消息数字|16|WM_CLOSE|  
|!|原始格式，忽略任何数据类型视图自定义项|\<customized representation>|4|  
  
> [!NOTE]
>  当**hv**格式说明符，调试器会尝试确定缓冲区的长度并显示该数目的元素。 由于调试器并非总是可以查找确切的数组缓冲区大小，只要可能时，就应该使用大小说明符 `(pBuffer,[bufferSize])` 。 **Hv**格式说明符时，缓冲区大小尚不可用  
  
###  <a name="BKMK_Size_specifiers_for_pointers_as_arrays_in_Visual_Studio_2012"></a> 指针的大小说明符作为数组  
 如果有一个指针指向要看做数组形式的对象，则可以使用一个整数或表达式来指定数组中元素的数量。 
  
|说明符|格式|原始监视值|显示的值|  
|---------------|------------|---------------------------|---------------------|  
|n|十进制或 **十六进制** 整数|pBuffer,[32]<br /><br /> pBuffer，“[0x20]”|将 `pBuffer` 显示为一个 32 元素的数组。|  
|**[exp]**|计算结果为一个整数的有效的 C++ 表达式。|pBuffer,[bufferSize]|将 pBuffer 显示为 `bufferSize` 元素的一个数组。|  
|**expand(n)**|计算结果为一个整数的有效的 C++ 表达式。|pBuffer, expand(2)|显示  `pBuffer`的第三个元素|  
  
##  <a name="BKMK_Format_specifiers_for_interop_debugging_and_C___edit_and_continue"></a> 使用 C++/CLI 的互操作调试的格式说明符  
 **粗体** 的说明符仅支持本地调试和 C++/CLI 代码。  
  
|说明符|格式|原始监视值|显示的值|  
|---------------|------------|--------------------------|---------------------|  
|**d**<br /><br />**i**|有符号的十进制整数|0xF000F065|-268373915|  
|**u**|无符号的十进制整数|0x0065|101|  
|o|无符号的八进制整数|0xF065|0170145|  
|x<br /><br />X|十六进制整数|61541|0x0000f065|  
|**l**<br /><br />**h**|用于 d、i、u、o、x、X 的 long 或 short 前缀|00406042|0x0c22|  
|**f**|带符号的浮点|(3./2.), f|1.500000|  
|**e**|有符号的科学计数法|(3.0/2.0)|1.500000e+000|  
|**g**|带符号浮点数或带符号的科学记数法，<br/> 较短者为准|(3.0/2.0)|1.5|  
|c|单个字符|\<location>|101 'e'|  
|秒|const char * （用引号引起来）|\<location>|"hello world"|  
|su|const wchar_t*<br /><br /> const char16_t\* （用引号引起来）|\<location>|L"hello world"|  
|sub|const wchar_t*<br /><br /> const char16_t\*|\<location>|hello world|  
|s8|const char * （用引号引起来）|\<location>|"hello world"|  
|hr|HRESULT 或 Win32 错误代码。<br/>Hresult 为不再需要此说明符，因为调试器自动将它们进行解码。|S_OK|S_OK|  
|wc|窗口类标志|0x00000040,|WC_DEFAULTCHAR|  
|wm|Windows 消息数字|0x0010|WM_CLOSE|  
|!|原始格式，忽略任何数据类型视图自定义项|\<customized representation>|4|  
  
###  <a name="BKMK_Format_specifiers_memory_locations_in_interop_debugging_and_C___edit_and_continue"></a> 格式说明符内存位置在互操作调试中使用 C + + /cli CLI  
 下表描述了用于内存位置的格式化符号。 可以使用带有计算为位置的任何值或表达式的内存位置说明符。  
  
|符号|格式|原始监视值|显示的值|  
|------------|------------|--------------------------|---------------------|  
|**ma**|64 个 ASCII 字符|0x0012ffac|0x0012ffac .4...0...".0W&.......1W&.0.:W..1...."..1.JO&.1.2.."..1...0y....1|  
|**m**|以十六进制表示的 16 个字节，后跟 16 个 ASCII 字符|0x0012ffac|0x0012ffac B3 34 CB 00 84 30 94 80 FF 22 8A 30 57 26 00 00 .4...0...".0W&amp;.|  
|**mb**|以十六进制表示的 16 个字节，后跟 16 个 ASCII 字符|0x0012ffac|0x0012ffac B3 34 CB 00 84 30 94 80 FF 22 8A 30 57 26 00 00 .4...0...".0W&amp;.|  
|**mw**|8 个字|0x0012ffac|0x0012ffac 34B3 00CB 3084 8094 22FF 308A 2657 0000|  
|**md**|4 个双字|0x0012ffac|0x0012ffac 00CB34B3 80943084 308A22FF 00002657|  
|**mq**|2 个双字|0x0012ffac|0x0012ffac 7ffdf00000000000 5f441a790012fdd4|  
|**mu**|双字节字符 (Unicode)|0x0012ffac|0x0012ffac 8478 77f4 ffff ffff 0000 0000 0000 0000|  
  
###  <a name="BKMK_Size_specifier_for_pointers_as_arrays_in_interop_debugging_and_C___edit_and_continue"></a> 指针的大小说明符，并且指针在使用 C++/CLI 进行的互操作调试中作为数组存在  
 如果有一个指针指向要看做数组形式的对象，则可以使用一个整数来指定数组中元素的数量。
  
|说明符|格式|表达式|显示的值|  
|---------------|------------|----------------|---------------------|  
|n|十进制整数|pBuffer[32]|将 `pBuffer` 显示为 32 个元素的数组。|
