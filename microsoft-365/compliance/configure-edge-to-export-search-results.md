---
title: Microsoft Edge で Office 365 eDiscovery エクスポートツールを使用する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft Edge を使用して、セキュリティ/コンプライアンスセンターでコンテンツ検索および電子情報開示から検索結果をエクスポートするには、ClickOnce サポートを有効にする必要があります。
ms.openlocfilehash: db70b4cdbc57f519db3b6b962eb8aa43585ba335
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42078584"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a>Microsoft Edge で Office 365 eDiscovery エクスポートツールを使用する

Microsoft Edge に対する最近の変更の結果として、ClickOnce のサポートは既定で有効になっていません。 Microsoft Office 365 eDiscovery エクスポートツールを引き続き使用して、コンテンツ検索や電子情報開示の検索結果をダウンロードするには、microsoft [Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads)を使用するか、microsoft Edge で ClickOnce サポートを有効にする必要があります。

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a>Microsoft Edge で ClickOnce サポートを有効にする方法

1. Microsoft Edge で、 **edge://flags/#edge**に移動します。

2. ドロップダウンリストで既存の値が**Default**または**Disabled**に設定されている場合は、[**有効**] に変更します。
    
   ![](../media/ClickOnceimage1.png)

3. ブラウザーウィンドウの一番下までスクロールし、[**再起動**] をクリックして、エッジを再起動します。

   ![](../media/ClickOnceimage2.png)

**注:** 組織は、グループポリシーを使用して ClickOnce サポートを無効にすることができます。 ClickOnce サポート用の組織ポリシーがあるかどうかを確認するには、 **edge://policy**に移動します。 次のスクリーンショットは、組織全体で ClickOnce が有効になっていることを示しています。 このポリシー値が**false**に設定されている場合は、組織の管理者に連絡する必要があります。

![](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a>Office 365 eDiscovery エクスポートツールをインストールして実行する

1. コンテンツ検索または電子情報開示ケースのエクスポートのポップアップページにある [**結果のダウンロード**] をクリックします。

   ![検索結果をダウンロードするには、ポップアップページの [結果のダウンロード] をクリックします。](../media/ClickOnceExport1.png)

2. ツールを起動するかどうかを確認するメッセージが表示されたら、[**開く**] をクリックします。

   ![[開く] をクリックして電子情報開示エクスポートツールを起動します。](../media/ClickOnceimage4.png)

   Microsoft Office 365 eDiscovery エクスポートツールがインストールされていない場合は、セキュリティの警告が表示されます。 

   ![[インストール] をクリックして電子情報開示エクスポートツールをインストールします。](../media/ClickOnceimage5.png)

3. **[インストール]** をクリックします。 インストール後、エクスポートツールが自動的に起動します。

詳細については、次のトピックをご覧ください。

- [コンテンツ検索の結果をエクスポートする](export-search-results.md)

- [Microsoft Edge で実験フラグを有効にする方法](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
