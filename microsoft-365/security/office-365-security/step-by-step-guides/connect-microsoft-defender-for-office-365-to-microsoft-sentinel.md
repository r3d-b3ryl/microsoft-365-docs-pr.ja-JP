---
title: Microsoft Defender for Office 365 を Microsoft Sentinel に接続する
description: Sentinel にMicrosoft Defender for Office 365接続する手順。 Microsoft Defender for Office 365 データ (*および* インシデントを含む、Microsoft 365 Defender スイートの残りの部分からのデータ) を Microsoft Sentinel に追加して、セキュリティに 1 つのウィンドウを追加します。
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: dbdb4c93ea010959c8f2eae61f9add8ea853d2b1
ms.sourcegitcommit: a7c1acfb3d2cbba913e32493b16ebd8cbfeee456
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66994329"
---
# <a name="connect-microsoft-defender-for-office-365-to-microsoft-sentinel"></a>Microsoft Defender for Office 365 を Microsoft Sentinel に接続する

インシデントを含む、Microsoft Defender for Office 365 データ (*および* Microsoft 365 Defender スイートの残りの部分からのデータ) を Microsoft Sentinel に取り込むことができます。

他の Microsoft 365 ソースからのデータ、インシデントとアラートの同期、高度な捜索と組み合わされた豊富なセキュリティ情報イベント管理 (SIEM) を利用します。

> [!IMPORTANT]
> Microsoft 365 Defender コネクタは現在 **プレビュー段階です**。 ベータ版、プレビュー版、またはまだ一般提供にリリースされていない Azure 機能に適用される追加の法的条件については、Microsoft Azure Previews の追加使用条件を参照してください。>

## <a name="what-you-will-need"></a>必要なもの
- Microsoft Defender for Office 365プラン 2 以降。 (E5 プランに含まれる)
- Microsoft Sentinel [クイック スタート ガイド](/azure/sentinel/quickstart-onboard)。
- 十分なアクセス許可 (M365 のセキュリティ管理者& Sentinel での読み取り/書き込みアクセス許可)。

## <a name="add-the-microsoft-365-defender-connector"></a>Microsoft 365 Defender コネクタを追加する
1. [Azure Portal にログインし、](https://portal.azure.com)**Microsoft Sentinel** >に移動します。関連するワークスペースを選択して、Microsoft 365 Defenderと対話します。
    1. 見出しの下にある左側のナビゲーション メニューの **[構成]** > [ **データ コネクタ**] を選択します。
2. ページが読み込まれたら、Microsoft 365 Defender **を検索****し、Microsoft 365 Defender (プレビュー) コネクタを選択します**。
3. 右側のポップアップで、[ **コネクタ ページを開く**] を選択します。
4. 読み込むページの **[構成]** セクションで、[ **インシデント&アラートの接続**] を選択し、これらの製品のすべての Microsoft インシデント作成ルールをオフにします。
5. ページの **[****接続イベント**] セクションでMicrosoft Defender for Office 365までスクロールします。 **EmailEvents、EmailUrlInfo、EmailAttachmentInfo & EmailPostDeliveryEvents** を選択し、ページの下部に **変更を適用** します。 (役に立ち、該当する場合は、この手順で他の Defender 製品からテーブルを選択します)。

## <a name="next-steps"></a>次の手順

管理者は、Microsoft Sentinel でインシデント、アラート、生データを表示できるようになり、このデータを *高度な捜索* に使用し、Microsoft Defender の既存のデータと新しいデータをピボットできます。

## <a name="more-information"></a>詳細情報

[Microsoft 365 Defender データを Microsoft Sentinel |に接続するMicrosoft Docs](/azure/sentinel/connect-microsoft-365-defender?tabs=MDE)

[Microsoft Teams を Microsoft Sentinel に接続する](/microsoftteams/teams-sentinel-guide)
