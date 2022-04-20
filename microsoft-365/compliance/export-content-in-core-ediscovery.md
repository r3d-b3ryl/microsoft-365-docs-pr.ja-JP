---
title: 電子情報開示 (Standard) ケースからコンテンツをエクスポートおよびダウンロードする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.custom: admindeeplinkCOMPLIANCE
description: Microsoft 365の電子情報開示 (Standard) ケースからコンテンツをエクスポートおよびダウンロードする方法について説明します。
ms.openlocfilehash: 2a63d22c8b4cb20e2c0f1317a8496e1cf517b2da
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64995450"
---
# <a name="export-content-from-a-ediscovery-standard-case"></a>電子情報開示 (Standard) ケースからコンテンツをエクスポートする

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview 電子情報開示 (Standard) ケースに関連付けられた検索が正常に実行されたら、検索結果をエクスポートできます。 検索結果をエクスポートすると、PST ファイルまたは個々のメッセージとしてメールボックス アイテムがダウンロードされます。 SharePoint サイトやOneDrive for Business サイトからコンテンツをエクスポートすると、ネイティブ Office ドキュメントやその他のドキュメントのコピーがエクスポートされます。 エクスポートされたすべてのアイテムに関する情報を含むResults.csv ファイルと、すべての検索結果に関する情報を含むマニフェスト ファイル (XML 形式) もエクスポートされます。
  
## <a name="export-search-results"></a>検索結果をエクスポートする

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>に移動し、適切な電子情報開示アクセス許可が割り当てられているユーザー アカウントの資格情報を使用してサインインします。

2. コンプライアンス ポータルの左側のナビゲーション ウィンドウで、[**すべて表示**] を選択し、**eDiscoveryCore** >  を選択します。<a href="https://go.microsoft.com/fwlink/p/?linkid=2174007" target="_blank"></a>

3. **[電子情報開示 (Standard)]** ページで、保留リストを作成するケースの名前をクリックします。

4. ケースの **ホーム** ページで、[ **検索** ] タブをクリックします。

5. ポップアップ ページの下部にある **[アクション]** メニューで、[ **結果のエクスポート**] をクリックします。

   ![[アクション] メニューの [結果のエクスポート] オプション。](../media/ActionMenuExportResults.png)

   電子情報開示 (Standard) ケースに関連付けられた検索の結果をエクスポートするワークフローは、 **コンテンツ検索** ページで検索の検索結果をエクスポートする場合と同じです。 詳細な手順については、「 [コンテンツ検索結果をエクスポート](export-search-results.md)する」を参照してください。

   > [!NOTE]
   > 検索されたメールボックスで同じメール メッセージの複数のインスタンスが検出された可能性がある場合でも、検索結果をエクスポートするときに、メール メッセージの 1 つのコピーのみがエクスポートされるようにする重複除去オプションを有効にできます。重複除去および重複したアイテムの特定方法の詳細については、「[電子情報開示検索結果での重複除去](de-duplication-in-ediscovery-search-results.md)」を参照してください。

   エクスポートを開始すると、検索結果はダウンロードの準備が整います。つまり、Microsoft クラウド内の Microsoft 提供のAzure Storageの場所に転送されます。
  
6. ケースの [ **エクスポート** ] タブをクリックして、エクスポート ジョブの一覧を表示します。
  
   ![電子情報開示 (Standard) ケースの [エクスポート] タブでジョブをエクスポートします。](../media/CoreeDiscoveryExport.png)

   エクスポート ジョブの一 **覧を更新** して、作成したエクスポート ジョブが表示されるように更新する必要がある場合があります。 エクスポート ジョブの名前は、対応する検索と同じ名前で、 **_Export** 検索名に追加されます。

7. 作成したエクスポート ジョブをクリックして、ポップアップ ページに状態情報を表示します。 この情報には、Azure Storage の場所に転送されたアイテムの割合が含まれます。

8. すべてのアイテムが転送されたら、[ **結果のダウンロード** ] をクリックして検索結果をローカル コンピューターにダウンロードします。 検索結果のダウンロードの詳細については、「コンテンツ検索結果を[エクスポート](export-search-results.md#step-2-download-the-search-results)する」の手順 2 を参照してください。

> [!NOTE]
> エクスポートされた検索結果は、エクスポート ジョブを作成してから 14 日以内にダウンロードする必要があります。

### <a name="more-information-about-exporting-searches-from-a-case"></a>ケースからの検索のエクスポートの詳細

- 検索結果をエクスポートするときに含まれるエクスポート ファイルの詳細については、「 [コンテンツ検索レポートをエクスポートする](export-a-content-search-report.md#whats-included-in-the-report)」を参照してください。

- エクスポートを再開した場合、エクスポート ジョブを構成する検索のクエリに対する変更は、取得される検索結果には影響しません。 エクスポートを再起動すると、エクスポート ジョブの作成時に実行されたのと同じ複合検索クエリ ジョブが再度実行されます。

- また、エクスポートを再起動すると、Azure Storageの場所にコピーされた検索結果によって前の結果が上書きされます。 コピーされた前の結果はダウンロードできません。
