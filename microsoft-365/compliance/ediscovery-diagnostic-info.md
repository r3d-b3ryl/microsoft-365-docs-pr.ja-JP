---
title: 電子情報開示の診断情報を収集する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft サポート案件の電子情報開示診断情報を収集する方法について説明します。
ms.openlocfilehash: 107309748e2f27b50be5f8e8fc76afcb693989f9
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944394"
---
# <a name="collect-ediscovery-diagnostic-information"></a>電子情報開示の診断情報を収集する

Microsoft サポートエンジニアは、コア電子情報開示または Advanced 電子情報開示に関連したサポート事例を開く際に、問題に関する特定の情報を必要とします。 この記事では、エンジニアによる問題の調査および解決に役立つ診断情報を収集する方法について説明します。 通常、Microsoft サポートエンジニアによる指示があるまで、この情報を収集する必要はありません。

> [!IMPORTANT]
> この記事に記載されているコマンドレットと診断情報の出力には、組織内の訴訟や内部調査に関する機密情報が含まれている場合があります。 生の診断情報を Microsoft サポートに送信する前に、情報を確認し、機密情報 (他者に関する名前やその他の情報など) をに置き換えて、その情報を消し `XXXXXXX` ます。 この方法を使用すると、Microsoft サポートエンジニアに情報ががされたことも示されます。

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>コア電子情報開示の診断情報を収集する

コア電子情報開示の診断情報の収集はコマンドレットベースなので、セキュリティ & コンプライアンスセンターの PowerShell を使用する必要があります。 次の PowerShell の例では、コマンドレットを実行し、指定したテキストファイルに出力を保存します。 ほとんどのサポートされている場合は、次のいずれかのコマンドのみを実行する必要があります。

次のコマンドレットを実行するには、[セキュリティ & コンプライアンス </span> センター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)します。 接続した後、次のコマンドを1つ以上実行し、プレースホルダーを実際のオブジェクト名に置き換えてください。

生成されたテキストファイルと赤の機密情報を確認した後、ケースで作業している Microsoft サポートエンジニアに送信します。

> [!NOTE]
> このセクションのコマンドを実行して、Microsoft 365 コンプライアンスセンターの [ **コンテンツ検索** ] ページにリストされている検索とエクスポートに関する診断情報を収集することもできます。

### <a name="collect-information-about-searches"></a>検索に関する情報を収集する

次のコマンドは、コンテンツ検索に関する問題を調査するときに役立つ情報を収集します。または、コア電子情報開示ケースに関連付けられている検索を実行します。

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>検索アクションに関する情報を収集する

次のコマンドは、主要な電子情報開示ケースに関連付けられたコンテンツ検索または検索結果のプレビュー、エクスポート、または削除に関する問題を調査するための情報を収集します。 [ **エクスポート** ] タブに一覧表示されているエクスポートをクリックすると、検索アクションの名前を識別できます。プレビューおよび削除アクションの名前を特定するには、 **new-compliancesearchaction** コマンドレットを実行して、すべてのアクションの一覧を表示できます。 検索アクション名の形式は、、、 `_Preview` `_Export` または `_Purge` 対応する検索の名前によって構成されます。

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>電子情報開示の保持に関する情報を収集する

コア電子情報開示ケースに関連付けられている電子情報開示保持が期待どおりに機能していない場合は、次のコマンドを実行して、電子情報開示保持のケースホールドポリシーおよび関連するケース保持ルールに関する情報を収集します。 次のコマンドの *ケース保持ポリシー名* は、電子情報開示ホールドの名前と同じです。 この名前は、コア電子情報開示ケースの **ホールド** タブで識別できます。

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>すべてのケース情報を収集する

場合によっては、Microsoft サポートが問題を調査するために必要な情報がわからないことがあります。 このような状況では、コア電子情報開示ケースの診断情報をすべて収集できます。 次のコマンドの *コア電子情報開示ケース名* は、Microsoft 365 コンプライアンスセンターの **コア電子情報開示** ページに表示されるケースの名前と同じです。

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{"$($_.Name)";"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>高度な電子情報開示の診断情報を収集する

高度な電子情報開示ケースの [ **設定** ] タブでは、ケースの診断情報をすばやくコピーできます。 診断情報は、テキストファイルに貼り付けて Microsoft サポートに送信できるように、クリップボードに保存されます。

1. に移動 [https://compliance.microsoft.com](https://compliance.microsoft.com/) し、[ **> すべての電子情報開示 > 詳細]** をクリックします。

2. ケースを選択し、[ **設定** ] タブをクリックします。

3. [ **ケース情報** ] で、[ **選択** ] をクリックします。

4. [ポップアップ] ページで、[ **診断情報のコピー** ] をクリックして情報をクリップボードにコピーします。

5. メモ帳でテキストファイルを開き、その情報をテキストファイルに貼り付けます。

6. テキストファイルを保存して、次のように名前を付け `AeD Diagnostic Info YYYY.MM.DD` ます (たとえば、 `AeD Diagnostic Info 2020.11.03` )。

ファイルの内容を確認し、機密情報が赤で処理された後、ケースで作業している Microsoft サポートエンジニアに送信します。
