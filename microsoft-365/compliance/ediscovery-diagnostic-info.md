---
title: 電子情報開示の診断情報を収集する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: Microsoft サポート ケースの電子情報開示診断情報を収集する方法について説明します。
ms.openlocfilehash: 2759156a3948339629ea7d988eaaa5464da197fa
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095886"
---
# <a name="collect-ediscovery-diagnostic-information"></a>電子情報開示の診断情報を収集する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview 電子情報開示 (Standard) または Microsoft Purview 電子情報開示 (プレミアム) に関連するサポート ケースを開くときに、Microsoft サポートエンジニアが問題に関する特定の情報を必要とする場合があります。 この記事では、エンジニアが問題を調査して解決するのに役立つ診断情報を収集する方法に関するガイダンスを提供します。 通常、Microsoft サポート エンジニアから要求されるまで、この情報を収集する必要はありません。

> [!IMPORTANT]
> この記事で説明するコマンドレットと診断情報からの出力には、組織内の訴訟または内部調査に関する機密情報が含まれる場合があります。 未加工の診断情報をMicrosoft サポートに送信する前に、情報を確認し、機密情報 (訴訟または調査の当事者に関する名前やその他の情報など) を編集`XXXXXXX`する必要があります。 このメソッドを使用すると、Microsoft サポート エンジニアにも情報が編集されたことを示します。

## <a name="collect-diagnostic-information-for-ediscovery-standard"></a>電子情報開示の診断情報を収集する (Standard)

電子情報開示 (Standard) の診断情報の収集はコマンドレットベースであるため、Security & Compliance Center PowerShell を使用する必要があります。 次の PowerShell の例では、コマンドレットを実行し、指定したテキスト ファイルに出力を保存します。 ほとんどのサポート ケースでは、これらのコマンドの 1 つだけを実行する必要があります。

次のコマンドレットを実行するには、 [Security & Compliance Center PowerShell に接続します</span>](/powershell/exchange/connect-to-scc-powershell)。 接続したら、次のコマンドのうち 1 つ以上を実行し、プレースホルダーを実際のオブジェクト名に置き換えてください。

生成されたテキスト ファイルを確認し、機密情報を編集した後、ケースで作業しているMicrosoft サポート エンジニアに送信します。

> [!NOTE]
> このセクションのコマンドを実行して、Microsoft Purview コンプライアンス ポータルの **コンテンツ検索** ページに一覧表示されている検索とエクスポートの診断情報を収集することもできます。

### <a name="collect-information-about-searches"></a>検索に関する情報を収集する

次のコマンドは、コンテンツ検索または電子情報開示 (Standard) ケースに関連する検索に関する問題を調査するときに役立つ情報を収集します。

```powershell
Get-ComplianceSearch "<Search name>" | FL > "ComplianceSearch.txt"
```

### <a name="collect-information-about-search-actions"></a>検索アクションに関する情報を収集する

次のコマンドは、コンテンツ検索または電子情報開示 (Standard) ケースに関連付けられた検索の結果のプレビュー、エクスポート、または削除に関する問題を調査するための情報を収集します。 [ **エクスポート** ] タブに一覧表示されているエクスポートをクリックすると、検索アクションの名前を識別できます。プレビューアクションと消去アクションの名前を識別するには、 **Get-ComplianceSearchAction** コマンドレットを実行して、すべてのアクションの一覧を表示します。 検索アクション名の形式は、対応する検索の名前に追加するか、`_Export`または`_Purge`追加`_Preview`することによって作成されます。

```powershell
Get-ComplianceSearchAction "<Search action name>" | FL > "ComplianceSearchAction.txt"
```

### <a name="collect-information-about-ediscovery-holds"></a>電子情報開示保留に関する情報を収集する

電子情報開示 (Standard) ケースに関連付けられている電子情報開示ホールドが期待どおりに機能しない場合は、次のコマンドを実行して、ケースホールド ポリシーと電子情報開示ホールドに関連するケースホールド ルールに関する情報を収集します。 次のコマンドの *ケース ホールド ポリシー名* は、電子情報開示ホールドの名前と同じです。 この名前は、電子情報開示 (Standard) ケースの **[保留]** タブで識別できます。

```powershell
Get-CaseHoldPolicy "<Case hold policy name>" | %{"--CaseHoldPolicy--";$_|FL;"--CaseHoldRule--";Get-CaseHoldRule -Policy $_.Name | FL} > "eDiscoveryCaseHold.txt"
```

### <a name="collect-all-case-information"></a>すべてのケース情報を収集する

場合によっては、問題を調査するためにMicrosoft サポートが必要とする情報が明らかでない場合があります。 このような場合は、電子情報開示 (Standard) ケースのすべての診断情報を収集できます。 次のコマンドの *電子情報開示 (Standard) ケース名* は、コンプライアンス ポータルの **電子情報開示 (Standard)** ページに表示されるケースの名前と同じです。

```powershell
Get-ComplianceCase "<eDiscovery (Standard) case name>"| %{$_|fl;"`t==Searches==";Get-ComplianceSearch -Case $_.Name | FL;"`t==Search Actions==";Get-ComplianceSearchAction -Case $_.Name |FL;"`t==Holds==";Get-CaseHoldPolicy -Case $_.Name | %{$_|FL;"`t`t ==$($_.Name) Rules==";Get-CaseHoldRule -Policy $_.Name | FL}} > "eDiscoveryCase.txt"
```

## <a name="collect-diagnostic-information-for-ediscovery-premium"></a>電子情報開示の診断情報を収集する (プレミアム)

電子情報開示 (**プレミアム**) ケースの [設定] タブでは、ケースの診断情報をすばやくコピーできます。 診断情報はクリップボードに保存されるため、テキスト ファイルに貼り付けてMicrosoft サポートに送信できます。

1. コンプライアンス ポータルに移動し、<a href="https://go.microsoft.com/fwlink/p/?linkid=2174006" target="_blank">**eDiscoveryAdvanced**</a> >  を選択します。

2. ケースを選択し、[**設定**] タブをクリックします。

3. [ **ケース情報**] の [選択] をクリック **します**。

4. ポップアップ ページで[**ActionsCopy のサポート情報****]** > をクリックして、情報をクリップボードにコピーします。

5. テキスト ファイル (メモ帳 で) を開き、テキスト ファイルに情報を貼り付けます。

6. テキスト ファイルを保存し、次のような`AeD Diagnostic Info YYYY.MM.DD`名前を付けます (たとえば)。 `AeD Diagnostic Info 2020.11.03`

ファイルを確認し、機密情報を編集した後、ケースに取り組んでいるMicrosoft サポート エンジニアに送信します。
