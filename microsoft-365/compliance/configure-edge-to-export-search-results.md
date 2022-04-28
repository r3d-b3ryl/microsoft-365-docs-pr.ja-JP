---
title: Microsoft Edgeで電子情報開示エクスポート ツールを使用する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 最新バージョンのMicrosoft Edgeを使用して、セキュリティとコンプライアンス センターでコンテンツ検索と電子情報開示から検索結果をダウンロードするには、ClickOnceサポートを有効にする必要があります。
ms.openlocfilehash: 13556b08a0eaec5ed11bdaf09014a3988cd56829
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092439"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>Microsoft Edgeで電子情報開示エクスポート ツールを使用する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

最新バージョンのMicrosoft Edgeに対する最近の変更の結果、ClickOnceサポートは既定で有効にされなくなりました。 引き続き電子情報開示エクスポート ツールを使用してコンテンツ検索または電子情報開示の検索結果をダウンロードするには、[Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) を使用するか、最新バージョンのMicrosoft EdgeでClickOnceサポートを有効にする必要があります。

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Microsoft EdgeでClickOnceサポートを有効にする

1. Microsoft Edgeで、edge://flags/#edge-click-once に移動 **します**。

2. ドロップダウン リストで既存の値が **[既定値]** または **[無効]** に設定されている場合は、[ **有効]** に変更します。

   ![ドロップダウン リストから [有効] を選択します。](../media/ClickOnceimage1.png)

3. ブラウザー ウィンドウの下部まで下にスクロールし、[ **再起動]** をクリックして Edge を再起動します。

   ![[再起動] をクリックします。](../media/ClickOnceimage2.png)

**メモ：** 組織はグループ ポリシーを使用して、ClickOnceサポートを無効にすることができます。 ClickOnceサポートの組織ポリシーがあるかどうかを確認するには、**edge://policy** に移動します。 次のスクリーンショットは、組織全体でClickOnceが有効になっていることを示しています。 このポリシー値が **false** に設定されている場合は、組織内の管理者に連絡する必要があります。

![Edge 組織ポリシーの一覧。](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>電子情報開示エクスポート ツールをインストールして実行する

1. コンテンツ検索または電子情報開示ケースのエクスポートのポップアップ ページで [ **結果のダウンロード** ] をクリックします。

   ![ポップアップ ページで [結果のダウンロード] をクリックして、検索結果をダウンロードします。](../media/ClickOnceExport1.png)

2. ツールを起動する確認メッセージが表示されたら、[ **開く**] をクリックします。

   ![[開く] をクリックして電子情報開示エクスポート ツールを起動します。](../media/ClickOnceimage4.png)

   電子情報開示エクスポート ツールがインストールされていない場合は、セキュリティ警告が表示されます。 

   ![[インストール] をクリックして、電子情報開示エクスポート ツールをインストールします。](../media/ClickOnceimage5.png)

3. **[インストール]** をクリックします。 インストールすると、エクスポート ツールが自動的に起動します。

詳細については、次のトピックをご覧ください。

- [コンテンツ検索の結果をエクスポートする](export-search-results.md)

- [Microsoft Edgeで実験フラグを有効にする方法](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
