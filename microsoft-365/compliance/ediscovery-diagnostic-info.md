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
description: Microsoft サポート ケースの電子情報開示診断情報を収集する方法について説明します。
ms.openlocfilehash: e5dd4f9bd26121fd5879b2322549a801a3376be0
ms.sourcegitcommit: 132b8dc316bcd4b456de33d6a30e90ca69b0f956
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589348"
---
# <a name="collect-ediscovery-diagnostic-information"></a>電子情報開示の診断情報を収集する

場合によっては、Microsoft サポート エンジニアは、Core eDiscovery または電子情報開示に関連するサポート ケースを開く際に、問題に関する特定の情報をAdvanced eDiscovery。 この記事では、サポート エンジニアが問題を調査および解決するために診断情報を収集する方法に関するガイダンスを提供します。 通常、Microsoft サポート エンジニアからこの情報の収集を求めるまで、この情報を収集する必要があります。

> [!IMPORTANT]
> この記事で説明するコマンドレットと診断情報からの出力には、組織内の訴訟や内部調査に関する機密情報が含まれる場合があります。 生の診断情報を Microsoft サポートに送信する前に、情報を確認し、機密情報 (訴訟や調査の関係者に関する名前や他の情報など) を置き換えてやり直す必要があります `XXXXXXX` 。 このメソッドを使用すると、Microsoft サポート エンジニアに情報が再編集されたというメッセージも表示されます。

## <a name="collect-diagnostic-information-for-core-ediscovery"></a>Core eDiscovery の診断情報を収集する

Core eDiscovery の診断情報の収集はコマンドレットベースなので、コンプライアンス センター PowerShell でセキュリティ &使用する必要があります。 次の PowerShell の例では、コマンドレットを実行し、指定したテキスト ファイルに出力を保存します。 ほとんどのサポートケースでは、これらのコマンドのいずれかを実行する必要があります。

次のコマンドレットを実行するには、コンプライアンス センター [PowerShell &に接続します </span> ](/powershell/exchange/connect-to-scc-powershell)。 接続が終わると、次の 1 つ以上のコマンドを実行し、プレースホルダーを実際のオブジェクト名に置き換える必要があります。

生成されたテキスト ファイルを確認し、機密情報を編集した後、ケースに取り組む Microsoft サポート エンジニアに送信します。

> [!NOTE]
> また、このセクションのコマンドを実行して、検索とエクスポートの診断情報を収集し、このセクションの[コンテンツ検索] ページに一覧表示Microsoft 365 コンプライアンス センター。

### <a name="collect-information-about-searches"></a>検索に関する情報を収集する

次のコマンドは、コンテンツ検索またはコア電子情報開示ケースに関連付けられた検索に関する問題を調査するときに役立つ情報を収集します。

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>検索アクションに関する情報を収集する

次のコマンドは、コンテンツ検索または Core 電子情報開示ケースに関連付けられた検索の結果をプレビュー、エクスポート、または削除する際の問題を調査するために情報を収集します。 [エクスポート] タブに表示されているエクスポートをクリックすると、検索アクションの名前 **を識別** できます。プレビューアクションと削除アクションの名前を識別するには **、Get-ComplianceSearchAction** コマンドレットを実行して、すべてのアクションの一覧を表示できます。 検索アクション名の形式は、対応する検索の名前に 、を追加 `_Preview` `_Export` `_Purge` して作成されます。

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>電子情報開示ホールドに関する情報を収集する

Core 電子情報開示ケースに関連付けられている電子情報開示ホールドが期待通り機能しない場合は、次のコマンドを実行して、電子情報開示ホールドのケースホールド ポリシーと関連付けられたケースホールド ルールに関する情報を収集します。 次 *のコマンドのケース* 保持ポリシー名は、電子情報開示ホールドの名前と同じです。 この名前は、コア電子 **情報開示ケースの [** 保留] タブで識別できます。

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>すべてのケース情報を収集する

Microsoft サポートが問題を調査するために必要な情報が明らかではない場合があります。 この状況では、コア電子情報開示ケースのすべての診断情報を収集できます。 次 *のコマンドのコア* 電子情報開示ケース名は、次のコマンドの [コア電子情報開示] ページに表示されるケースの名前と同Microsoft 365 コンプライアンス センター。

```powershell
Get-ComplianceCase "<Core eDiscovery case name>"| %{$_|fl;"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-advanced-ediscovery"></a>ユーザーの診断情報をAdvanced eDiscovery

ケース **設定** の [Advanced eDiscovery] タブを使用すると、ケースの診断情報をすばやくコピーできます。 診断情報はクリップボードに保存され、テキスト ファイルに貼り付け、Microsoft サポートに送信できます。

1. [電子情報開示 [https://compliance.microsoft.com](https://compliance.microsoft.com/) ] に移動し、[詳細] > **クリックします**。

2. ケースを選択し、[追加] タブ **設定** します。

3. [ケース **情報] で、[** 選択] **をクリックします**。

4. [フライアウト] ページで、[**アクション**  >  **] [サポート情報の** コピー] をクリックして、情報をクリップボードにコピーします。

5. テキスト ファイル (メモ帳) を開き、テキスト ファイルに情報を貼り付けます。

6. テキスト ファイルを保存し、名前を付けます `AeD Diagnostic Info YYYY.MM.DD` (たとえば `AeD Diagnostic Info 2020.11.03` )。

ファイルを確認して機密情報を編集した後、ケースに取り組む Microsoft サポート エンジニアに送信します。
