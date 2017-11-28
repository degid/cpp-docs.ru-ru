---
title: "Справочник по директивам | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Directives Reference
dev_langs: C++
helpviewer_keywords: MASM (Microsoft Macro Assembler), directives reference
ms.assetid: da6efcd1-18f7-41de-81cd-a002a02f9a22
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7493121bb4565e70c1638599496e4072fc527481
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="directives-reference"></a>Справочник по директивам
**x64**  
  
||||  
|-|-|-|  
|[.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)|[.ENDPROLOG](../../assembler/masm/dot-endprolog.md)|[PROC](../../assembler/masm/proc.md)|  
|[.PUSHFRAME](../../assembler/masm/dot-pushframe.md)|[.PUSHREG](../../assembler/masm/dot-pushreg.md)|[.SAVEREG](../../assembler/masm/dot-savereg.md)|  
|[.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)|[.SETFRAME](../../assembler/masm/dot-setframe.md)||  
  
### <a name="code-labels"></a>Метки кода  
  
|||  
|-|-|  
|[ВЫРАВНИВАНИЕ](../../assembler/masm/align-masm.md)|[EVEN](../../assembler/masm/even.md)|  
|[МЕТКА](../../assembler/masm/label-masm.md)|[ORG](../../assembler/masm/org.md)|  
  
### <a name="conditional-assembly"></a>Условные сборки  
  
||||  
|-|-|-|  
|[ELSE](../../assembler/masm/else-masm.md)|[ELSEIF](../../assembler/masm/elseif-masm.md)|[ELSEIF2](../../assembler/masm/elseif2.md)|  
|[ЕСЛИ](../../assembler/masm/if-masm.md)|[IF2](../../assembler/masm/if2.md)|[IFB](../../assembler/masm/ifb.md)/[IFNB](../../assembler/masm/ifnb.md)|  
|[IFDEF](../../assembler/masm/ifdef.md)/[IFNDEF:](../../assembler/masm/ifndef.md)|[IFDIF](../../assembler/masm/ifdif.md)/[IFDIF &#91; &#91; &#93; &#93;](../../assembler/masm/ifdif.md)|[IFE](../../assembler/masm/ife.md)|  
|[IFIDN](../../assembler/masm/ifidn.md)/[IFIDN &#91; &#91; &#93; &#93;](../../assembler/masm/ifidn.md)|||  
  
### <a name="conditional-control-flow"></a>Поток управления условного  
  
||||  
|-|-|-|  
|[.BREAK](../../assembler/masm/dot-break.md)|[.CONTINUE](../../assembler/masm/dot-continue.md)|[.ELSE](../../assembler/masm/dot-else.md)|  
|[. ELSEIF](../../assembler/masm/dot-if.md)|[.ENDIF](../../assembler/masm/dot-endif.md)|[.ENDW](../../assembler/masm/dot-endw.md)|  
|[.IF](../../assembler/masm/dot-if.md)|[.REPEAT](../../assembler/masm/dot-repeat.md)|[.UNTIL](../../assembler/masm/dot-until.md)|  
|[.UNTILCXZ](../../assembler/masm/dot-untilcxz.md)|[.WHILE](../../assembler/masm/dot-while.md)||  
  
### <a name="conditional-error"></a>Ошибка условной  
  
||||  
|-|-|-|  
|[.ERR](../../assembler/masm/dot-err.md)|[.ERR2](../../assembler/masm/dot-err2.md)|[.ERRB](../../assembler/masm/dot-errb.md)|  
|[.ERRDEF](../../assembler/masm/dot-errdef.md)|[. ERRDIF](../../assembler/masm/dot-errdif.md)/[. ERRDIF &#91; &#91; &#93; &#93; &#93;](../../assembler/masm/dot-errdif.md)|[.ERRE](../../assembler/masm/dot-erre.md)|  
|[. ERRIDN](../../assembler/masm/dot-erridn.md)/[. ERRIDN &#91; &#91; &#93; &#93;](../../assembler/masm/dot-erridn.md)|[.ERRNB](../../assembler/masm/dot-errnb.md)|[.ERRNDEF](../../assembler/masm/dot-errndef.md)|  
|[.ERRNZ](../../assembler/masm/dot-errnz.md)|||  
  
### <a name="data-allocation"></a>Размещение данных  
  
||||  
|-|-|-|  
|[ВЫРАВНИВАНИЕ](../../assembler/masm/align-masm.md)|[БАЙТОВ](../../assembler/masm/byte-masm.md)/[SBYTE](../../assembler/masm/sbyte-masm.md)|[DWORD](../../assembler/masm/dword.md)/[SDWORD](../../assembler/masm/sdword.md)|  
|[EVEN](../../assembler/masm/even.md)|[FWORD](../../assembler/masm/fword.md)|[МЕТКА](../../assembler/masm/label-masm.md)|  
|[ORG](../../assembler/masm/org.md)|[QWORD](../../assembler/masm/qword.md)|[REAL4](../../assembler/masm/real4.md)|  
|[REAL8](../../assembler/masm/real8.md)|[REAL10](../../assembler/masm/real10.md)|[TBYTE](../../assembler/masm/tbyte.md)|  
|[WORD](../../assembler/masm/word.md)/[SWORD](../../assembler/masm/sword.md)|||  
  
### <a name="equates"></a>Соответствует  
  
||  
|-|  
|[=](../../assembler/masm/equal.md)|  
|[EQU](../../assembler/masm/equ.md)|  
|[TEXTEQU](../../assembler/masm/textequ.md)|  
  
### <a name="listing-control"></a>Элемент управления списка  
  
||||  
|-|-|-|  
|[.CREF](../../assembler/masm/dot-cref.md)|[.LIST](../../assembler/masm/dot-list.md)|[.LISTALL](../../assembler/masm/dot-listall.md)|  
|[.LISTIF](../../assembler/masm/dot-listif.md)|[.LISTMACRO](../../assembler/masm/dot-listmacro.md)|[.LISTMACROALL](../../assembler/masm/dot-listmacroall.md)|  
|[.NOCREF](../../assembler/masm/dot-nocref.md)|[.NOLIST](../../assembler/masm/dot-nolist.md)|[.NOLISTIF](../../assembler/masm/dot-nolistif.md)|  
|[.NOLISTMACRO](../../assembler/masm/dot-nolistmacro.md)|[PAGE](../../assembler/masm/page.md)|[SUBTITLE](../../assembler/masm/subtitle.md)|  
|[.TFCOND](../../assembler/masm/dot-tfcond.md)|[TITLE](../../assembler/masm/title.md)||  
  
### <a name="macros"></a>Макросы  
  
||||  
|-|-|-|  
|[ENDM](../../assembler/masm/endm.md)|[EXITM](../../assembler/masm/exitm.md)|[ОПЕРАТОР GOTO](../../assembler/masm/goto-masm.md)|  
|[ЛОКАЛЬНЫЕ](../../assembler/masm/local-masm.md)|[MACRO](../../assembler/masm/macro.md)|[PURGE](../../assembler/masm/purge.md)|  
  
### <a name="miscellaneous"></a>Прочее  
  
||||  
|-|-|-|  
|[ПСЕВДОНИМ](../../assembler/masm/alias-masm.md)|[ASSUME](../../assembler/masm/assume.md)|[КОММЕНТАРИЙ](../../assembler/masm/comment-masm.md)|  
|[ECHO](../../assembler/masm/echo.md)|[КОНЕЦ](../../assembler/masm/end-masm.md)|[.FPO](../../assembler/masm/dot-fpo.md)|  
|[ВКЛЮЧИТЬ](../../assembler/masm/include-masm.md)|[INCLUDELIB](../../assembler/masm/includelib-masm.md)|[MMWORD](../../assembler/masm/mmword.md)|  
|[ПАРАМЕТР](../../assembler/masm/option-masm.md)|[POPCONTEXT](../../assembler/masm/popcontext.md)|[PUSHCONTEXT](../../assembler/masm/pushcontext.md)|  
|[.RADIX](../../assembler/masm/dot-radix.md)|[.SAFESEH](../../assembler/masm/dot-safeseh.md)|[XMMWORD](../../assembler/masm/xmmword.md)|  
|[YMMWORD](../../assembler/masm/ymmword.md)|||  
  
### <a name="procedures"></a>Процедуры  
  
||||  
|-|-|-|  
|[ENDP](../../assembler/masm/endp.md)|[INVOKE](../../assembler/masm/invoke.md)|[PROC](../../assembler/masm/proc.md)|  
|[PROTO](../../assembler/masm/proto.md)|||  
  
### <a name="processor"></a>Процессор  
  
||||  
|-|-|-|  
|[.386](../../assembler/masm/dot-386.md)|[.386P](../../assembler/masm/dot-386p.md)|[.387](../../assembler/masm/dot-387.md)|  
|[.486](../../assembler/masm/dot-486.md)|[.486P](../../assembler/masm/dot-486p.md)|[.586](../../assembler/masm/dot-586.md)|  
|[.586P](../../assembler/masm/dot-586p.md)|[.686](../../assembler/masm/dot-686.md)|[.686P](../../assembler/masm/dot-686p.md)|  
|[.K3D](../../assembler/masm/dot-k3d.md)|[.MMX](../../assembler/masm/dot-mmx.md)|[.XMM](../../assembler/masm/dot-xmm.md)|  
  
### <a name="repeat-blocks"></a>Повторите блоков  
  
||||  
|-|-|-|  
|[ENDM](../../assembler/masm/endm.md)|[ДЛЯ](../../assembler/masm/for-masm.md)|[FORC](../../assembler/masm/forc.md)|  
|[ОПЕРАТОР GOTO](../../assembler/masm/goto-masm.md)|[REPEAT](../../assembler/masm/repeat.md)|[WHILE](../../assembler/masm/while-masm.md)|  
  
### <a name="scope"></a>Область  
  
||||  
|-|-|-|  
|[COMM](../../assembler/masm/comm.md)|[EXTERN](../../assembler/masm/extern-masm.md)|[EXTERNDEF](../../assembler/masm/externdef.md)|  
|[INCLUDELIB](../../assembler/masm/includelib-masm.md)|[PUBLIC](../../assembler/masm/public-masm.md)||  
  
### <a name="segment"></a>Сегмент  
  
||||  
|-|-|-|  
|[.ALPHA](../../assembler/masm/dot-alpha.md)|[ASSUME](../../assembler/masm/assume.md)|[.DOSSEG](../../assembler/masm/dot-dosseg.md)|  
|[КОНЕЦ](../../assembler/masm/end-masm.md)|[ЗАКАНЧИВАЕТСЯ](../../assembler/masm/ends-masm.md)|[GROUP](../../assembler/masm/group.md)|  
|[SEGMENT](../../assembler/masm/segment.md)|[.SEQ](../../assembler/masm/dot-seq.md)||  
  
### <a name="simplified-segment"></a>Упрощенная сегмента  
  
||||  
|-|-|-|  
|[.CODE](../../assembler/masm/dot-code.md)|[.CONST](../../assembler/masm/dot-const.md)|[.DATA](../../assembler/masm/dot-data.md)|  
|[.DATA?](../../assembler/masm/dot-data-q.md)|[.DOSSEG](../../assembler/masm/dot-dosseg.md)|[.EXIT](../../assembler/masm/dot-exit.md)|  
|[.FARDATA](../../assembler/masm/dot-fardata.md)|[.FARDATA?](../../assembler/masm/dot-fardata-q.md)|[.MODEL](../../assembler/masm/dot-model.md)|  
|[.STACK](../../assembler/masm/dot-stack.md)|[.STARTUP](../../assembler/masm/dot-startup.md)||  
  
### <a name="string"></a>Строка  
  
|||  
|-|-|  
|[CATSTR](../../assembler/masm/catstr.md)|[INSTR](../../assembler/masm/instr.md)|  
|[SIZESTR](../../assembler/masm/sizestr.md)|[SUBSTR](../../assembler/masm/substr.md)|  
  
### <a name="structure-and-record"></a>Структуры и записи  
  
||||  
|-|-|-|  
|[ЗАКАНЧИВАЕТСЯ](../../assembler/masm/ends-masm.md)|[ЗАПИСЬ](../../assembler/masm/record-masm.md)|[СТРУКТУРА](../../assembler/masm/struct-masm.md)|  
|[ОПРЕДЕЛЕНИЕ ТИПА](../../assembler/masm/typedef-masm.md)|[UNION](../../assembler/masm/union.md)||  
  
## <a name="see-also"></a>См. также  
 [Справочные материалы по ассемблеру Microsoft Macro Assembler](../../assembler/masm/microsoft-macro-assembler-reference.md)