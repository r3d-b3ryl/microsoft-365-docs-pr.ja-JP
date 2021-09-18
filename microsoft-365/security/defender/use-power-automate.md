---
title: Power Automateを使用する
description: 電源の自動化について、Microsoft 365 Defenderの使い方について学習します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、カスタム検出、スキーマ、secops
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a707de259897080f8e726aed70618ea6505bdea6
ms.sourcegitcommit: 7e7effd8ef4ffe75cdee7bb8517fec8608e4c230
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2021
ms.locfileid: "59444117"
---
# <a name="use-power-automate-in-microsoft-365-defender"></a>[Power AutomateでMicrosoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験してみませんか? [ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。
>

最新のセキュリティ操作 (SecOps) チームは、効果的に機能するために自動化が必要です。 実際の脅威の検出と調査に集中するために、SecOps チームは Power Automate を使用してアラートの一覧をトリアージし、脅威ではない脅威を排除します。  

## <a name="criteria-for-resolving-alerts"></a>アラートを解決するための条件

- ユーザーがアウトオブオフィス メッセージを有効にしている

- ユーザーが高リスクとしてタグ付けされていない

両方が true の場合、SecOps はアラートを正当な移動としてマークし、解決します。 通知は、通知が解決Microsoft Teams後に通知に投稿されます。 

## <a name="connect-power-automate-to-microsoft-cloud-app-security"></a>Connect Power AutomateをMicrosoft Cloud App Security

オートメーションを作成するには、API トークンを必要としてから、API トークンを Power Automate (MCAS) Microsoft Cloud App Securityします。 

1. **[設定] をクリック** し **、[セキュリティ拡張機能]** を選択し、[API **トークン**] タブの [トークンの追加 **] をクリック** します。 

2. トークンの名前を指定し、[生成] を **クリックします**。 後で必要に応じてトークンを保存します。

## <a name="create-an-automated-flow"></a>自動フローの作成

詳細な手順については、ビデオを参照 [してください](https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn)。 

このビデオでは、電源自動化を MCAS に接続する方法も説明します。 

## <a name="related-information"></a>関連情報

- [アプリケーションPower Automate統合Microsoft Cloud App Security](/cloud-app-security/flow-integration)

- [Microsoft Power Automateドキュメント](/power-automate)
