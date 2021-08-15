---
title: コア電子情報開示ケースからコンテンツをエクスポートおよびダウンロードする
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: コア電子情報開示ケースからコンテンツをエクスポートおよびダウンロードする方法について説明します。Microsoft 365。
ms.openlocfilehash: c74cf79ffc5defe495ed03ac45182dbd8e36582418879d6cf367242b96095eb9
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53850822"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>コア電子情報開示ケースからコンテンツをエクスポートする

Core 電子情報開示ケースに関連付けられた検索が正常に実行された後、検索結果をエクスポートできます。 検索結果をエクスポートすると、メールボックス アイテムは PST ファイルまたは個々のメッセージとしてダウンロードされます。 サイトからコンテンツをエクスポートSharePoint、OneDrive for Businessドキュメントや他のドキュメントのOfficeコピーがエクスポートされます。 エクスポートResults.csvに関する情報を含むファイルと、すべての検索結果に関する情報を含むマニフェスト ファイル (XML 形式) もエクスポートされます。
  
## <a name="export-search-results"></a>検索結果をエクスポートする

1. 適切な電子情報開示アクセス許可が割り当てられているユーザー アカウントの資格情報を使用して、アクセスして [https://compliance.microsoft.com](https://compliance.microsoft.com) サインインします。

2. ウィンドウの左側のナビゲーション ウィンドウMicrosoft 365 コンプライアンス センター [すべて表示] をクリックし、[電子情報開示] [コア] **>クリックします**。

3. [コア **電子情報開示]** ページで、保留リストを作成するケースの名前をクリックします。

4. ケースの **ホーム** ページで、[検索] **タブをクリック** します。

5. [フライアウト **] ページ** の下部にある [操作] メニューで、[結果のエクスポート] **をクリックします**。

   ![[操作] メニューの [結果のエクスポート] オプション](../media/ActionMenuExportResults.png)

   Core 電子情報開示ケースに関連付けられた検索の結果をエクスポートするワークフローは、[コンテンツ検索] ページで検索の検索結果をエクスポートする場合 **と同** じです。 詳細な手順については、「コンテンツ検索結果のエクスポート [」を参照してください](export-search-results.md)。

   > [!NOTE]
   > 検索されたメールボックスで同じメール メッセージの複数のインスタンスが検出された可能性がある場合でも、検索結果をエクスポートするときに、メール メッセージの 1 つのコピーのみがエクスポートされるようにする重複除去オプションを有効にできます。重複除去および重複したアイテムの特定方法の詳細については、「[電子情報開示検索結果での重複除去](de-duplication-in-ediscovery-search-results.md)」を参照してください。

   エクスポートを開始すると、検索結果はダウンロード用に準備されます。つまり、検索結果は Microsoft クラウド内の Microsoft 提供のAzure Storageに転送されます。
  
6. ケースの **[エクスポート]** タブをクリックして、エクスポート ジョブの一覧を表示します。
  
   ![コア電子情報開示ケースの [エクスポート] タブでジョブをエクスポートする](../media/CoreeDiscoveryExport.png)

   [更新] を **クリックして** エクスポート ジョブの一覧を更新し、作成したエクスポート ジョブを表示する必要がある場合があります。 エクスポート ジョブの名前は、対応する検索と同じ名前で、_Export **に追加** されます。

7. 作成したエクスポート ジョブをクリックして、フライアウト ページに状態情報を表示します。 この情報には、ユーザーの場所に転送されたアイテムのAzure Storage含まれます。

8. すべてのアイテムが転送された後、[結果のダウンロード] **をクリックして** 、検索結果をローカル コンピューターにダウンロードします。 検索結果のダウンロードの詳細については、「コンテンツ検索結果のエクスポート」の「手順 [2」を参照してください。](export-search-results.md#step-2-download-the-search-results)

### <a name="more-information-about-exporting-searches-from-a-case"></a>ケースからの検索のエクスポートの詳細

- 検索結果をエクスポートするときに含まれるエクスポート ファイルの詳細については、「コンテンツ検索レポートのエクスポート [」を参照してください](export-a-content-search-report.md#whats-included-in-the-report)。

- エクスポートを再開した場合、エクスポート ジョブを構成する検索のクエリに対する変更は、取得される検索結果には影響を与えかねない。 エクスポートを再開すると、エクスポート ジョブの作成時に実行されたのと同じ検索クエリ ジョブが再度実行されます。

- また、エクスポートを再開すると、エクスポート先の場所にコピー Azure Storage結果が上書きされます。 コピーされた以前の結果はダウンロードできません。
