---
title: コンテキスト ファイルとフォルダーの除外
description: Windows 上の Microsoft Defender ウイルス対策のコンテキスト ファイルとフォルダーの除外機能について説明します。 この機能を使用すると、制限を適用して、Microsoft Defender ウイルス対策がファイルまたはフォルダーをスキャンしないコンテキストを定義するときに、より具体的にすることができます
keywords: Microsoft Defender ウイルス対策、プロセス、除外、ファイル、スキャン
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: jweston-1
ms.author: v-jweston
ms.localizationpriority: medium
ms.date: 08/25/2022
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 0868250b04120a4eed0cf254e4a9d3692eb661fa
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67477959"
---
# <a name="contextual-file-and-folder-exclusions"></a>コンテキスト ファイルとフォルダーの除外

この記事/セクションでは、Windows 上の Microsoft Defender ウイルス対策のコンテキスト ファイルとフォルダーの除外機能について説明します。 この機能を使用すると、Microsoft Defender ウイルス対策が制限を適用してファイルまたはフォルダーをスキャンしないコンテキストを定義するときに、より具体的にすることができます。

## <a name="overview"></a>概要

除外は、主にパフォーマンスへの影響を軽減することを目的としています。 保護価値の低下のペナルティが課されます。 これらの制限により、除外が適用される状況を指定することで、この保護の削減を制限できます。 コンテキストの除外は、信頼性の高い方法で誤検知に対処するのに適していません。 誤検知が発生した場合は、[Microsoft 365 Defender](https://security.microsoft.com/) ポータル (サブスクリプションが必要) または[Microsoft セキュリティ インテリジェンス](https://www.microsoft.com/wdsi/filesubmission) Web サイトを通じて分析のためにファイルを送信できます。 一時的な抑制方法の場合は、[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/indicator-file)でカスタム _許可_ インジケーターを作成することを検討してください。

除外の適用可能性を制限するには、次の 4 つの制限を適用できます。

- **ファイル/フォルダーのパスの種類の制限**。 除外を制限して適用できるのは、ターゲットがファイルの場合、または意図を特定することでフォルダーの場合のみです。 ターゲットがファイルで、除外がフォルダーとして指定されている場合は、適用されません。 逆に、ターゲットがフォルダーで、除外がファイルとして指定されている場合は、除外が適用されます。
- **スキャンの種類の制限**。 除外を適用するために必要なスキャンの種類を定義できます。 たとえば、特定のフォルダーを完全スキャンから除外するだけで、"リソース" スキャン (ターゲット スキャン) から除外することはできません。
- **スキャン トリガーの種類の制限**。 この制限を使用して、特定のイベントによってスキャンが開始されたときにのみ除外を適用するように指定できます。
  - オン デマンド
  - on access
  - または動作監視から発信される
- **プロセスの制限**。 特定のプロセスによってファイルまたはフォルダーにアクセスする場合にのみ除外を適用するように定義できます。

## <a name="configuring-restrictions"></a>制限の構成

制限は通常、制限の種類をファイルまたはフォルダーの除外パスに追加することによって適用されます。  

| Restriction | TypeName | 値 |
|:---|:---|:---|
| ファイル/フォルダー  | PathType  | file <br> folder |
| スキャンの種類 | ScanType | クイック <br> 完全 |
| スキャン トリガー | ScanTrigger | オンデマンド <br> OnAccess <br> Bm |
| プロセス | プロセス | "<image_path>" |

### <a name="requirements"></a>要件

この機能には、Microsoft Defender ウイルス対策が必要です。

- プラットフォーム: **4.18.2205.7** 以降
- エンジン: **1.1.19300.2** 以降

### <a name="syntax"></a>構文

出発点として、より具体的にしたい除外が既に設定されている場合があります。 除外文字列を形成するには、最初に除外するファイルまたはフォルダーへのパスを定義し、次に次の例に示すように、型名と関連付けられた値を追加します。

`<PATH>\:{TypeName:value,TypeName:value}`

_すべての_**型** と **値** では大文字と小文字が区別されます。

> [!NOTE]  
> 制限が一致するには、内部 `{}` の条件が true である必要があります。 たとえば、2 つのスキャン トリガーを指定した場合、これは true にできず、除外は適用されません。 同じ種類の 2 つの制限を指定するには、2 つの個別の除外を作成します。


### <a name="examples"></a>例

次の文字列は、"c:\documents\design.doc" がファイルの場合にのみ除外され、オンアクセス スキャンでのみ除外されます。

`c:\documents\design.doc\:{PathType:file,ScanTrigger:OnAccess}`

次の文字列は、イメージ名 "winword.exe" を持つプロセスによってアクセスされたためにスキャン (オンアクセス) された場合にのみ、"c:\documents\design.doc" を除外します。

`c:\documents\design.doc\:{Process:"winword.exe"}`

次の例のように、プロセス イメージパスにワイルドカードを含めることがあります。

`c:\documents\design.doc\:{Process:"C:\Program Files*\Microsoft Office\root\Office??\winword.exe"}`

### <a name="filefolder-restriction"></a>ファイル/フォルダーの制限

ターゲットがファイルまたはフォルダーの場合にのみ適用されるように除外を制限するには、意図を特定します。 ターゲットがファイルで、除外がフォルダーとして指定されている場合、除外は適用されません。 逆に、ターゲットがフォルダーで、除外がファイルとして指定されている場合は、除外が適用されます。

#### <a name="filefolder-exclusions-default-behavior"></a>ファイル/フォルダーの除外の既定の動作

他のオプションを指定しない場合、ファイル/フォルダーはすべての種類のスキャンから除外 _され_ 、ターゲットがファイルかフォルダーかに関係なく除外が適用されます。 特定のスキャンの種類にのみ適用されるように除外をカスタマイズする方法の詳細については、「 [スキャンの種類の制限](#scan-type-restriction)」を参照してください。

#### <a name="folders"></a>Folders

ターゲットがフォルダーの場合にのみ除外が適用されるようにするには、 **PathType:folder** 制限を使用できるファイルではありません。 以下に例を示します。

`C:\documents\:{PathType:folder}`

#### <a name="files"></a>Files

ターゲットがファイルの場合にのみ除外が適用されるようにするには、PathType: ファイルの制限を使用できるフォルダーではありません。

例:

`C:\documents\database.mdb\:{PathType:file}`

### <a name="scan-type-restriction"></a>スキャンの種類の制限

既定では、除外はすべてのスキャンの種類に適用されます。  

- **resource**: 1 つのファイルまたはフォルダーが対象の方法でスキャンされる (たとえば、右クリック、スキャン)
- **クイック**: マルウェア、メモリ、特定のレジストリ キーによって利用される一般的なスタートアップの場所
- **full**: クイック スキャンの場所と完全なファイル システム (すべてのファイルとフォルダー) が含まれます

パフォーマンスの問題を軽減するために、フォルダーまたは一連のファイルを特定のスキャンの種類でスキャンから除外できます。 除外を適用するために必要なスキャンの種類を定義することもできます。  

フル スキャン中にのみフォルダーをスキャン対象から除外するには、次の例に示すように、制限の種類をファイルまたはフォルダーの除外と共に指定します。

`C:\documents\:{ScanType:full}`

クイック スキャン中にのみフォルダーをスキャンから除外するには、ファイルまたはフォルダーの除外と共に制限の種類を指定します。

`C:\program.exe\:{ScanType:quick}`

この除外が特定のファイルにのみ適用され、フォルダーではなく (c:\foo.exeフォルダーである可能性がある) ことを確認する場合は、PathType 制限も適用されます。

`C:\program.exe\:{ScanType:quick,PathType:file}`

### <a name="scan-trigger-restriction"></a>スキャン トリガーの制限

既定では、すべてのスキャン トリガーに基本的な除外が適用されます。 ScanTrigger の制限を使用すると、特定のイベントによってスキャンが開始されたときにのみ除外を適用するように指定できます。オンデマンド (クイック スキャン、フル スキャン、ターゲット スキャンを含む)、アクセス時、または動作監視からの発信 (メモリ スキャンを含む)。

- **OnDemand**: コマンドまたは管理者のアクションによってスキャンがトリガーされました。 スケジュールされたクイック スキャンとフル スキャンも、このカテゴリに該当することを忘れないでください。
- **OnAccess**: ファイルまたはフォルダーが開かれる/書き込み/読み取り/変更される (通常はリアルタイム保護と見なされます)
- **BM**: 動作トリガーにより、動作監視によって特定のファイルがスキャンされます

ファイルまたはフォルダーとその内容を、アクセス後にスキャンするときにのみ除外するには、次の例のようなスキャン トリガーの制限を定義します。

`c:\documents\:{ScanTrigger:OnAccess}`

### <a name="process-restriction"></a>プロセスの制限

この制限により、除外が適用されるのは、特定のプロセスによってファイルまたはフォルダーにアクセスされている場合にのみ適用されるように定義できます。 一般的なシナリオは、その回避によって Defender ウイルス対策がそのプロセスによって他の操作を無視する原因となるので、プロセスを除外しないようにしたい場合です。

> [!NOTE]  
>
> コンピューターで大量のプロセス除外制限を使用すると、パフォーマンスに悪影響を与える可能性があります。  
> さらに、除外を特定のプロセスまたはプロセスに制限しているため、他のアクティブなプロセス (インデックス作成、バックアップ、更新など) は引き続きファイル スキャンをトリガーできます。

特定のプロセスによってアクセスされた場合にのみファイルまたはフォルダーを除外するには、通常のファイルまたはフォルダーの除外を作成し、除外を制限するプロセスを次のように追加します。  

`c:\documents\design.doc\:{Process:"winword.exe", Process:"msaccess.exe"}`

### <a name="how-to-configure"></a>構成する方法

必要なコンテキスト除外を作成した後、既存の管理ツールを使用して、作成した文字列を使用してファイルとフォルダーの除外を構成できます。

参照: [Microsoft Defender ウイルス対策スキャンの除外を構成して検証](configure-exclusions-microsoft-defender-antivirus.md)する
