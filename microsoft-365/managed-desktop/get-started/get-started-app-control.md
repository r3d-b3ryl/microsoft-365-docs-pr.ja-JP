---
title: アプリ制御の使用を開始する
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 3b1e74289046f7c04b77b25448af409966117fd9836f22dfdf813bdfd732b524
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53890961"
---
# <a name="get-started-with-app-control"></a>アプリ制御の使用を開始する

環境でアプリ制御を有効にする前に、アプリの実装方法と[](../service-description/app-control.md)Microsoft マネージド デスクトップ役割と責任を確認して理解してください。

Microsoft マネージド デスクトップ基本ポリシーを取得するより困難な側面を処理することで、アプリの制御を簡素化できます。 IT 管理者は、テスト リングでアプリをテストし、警告やエラーが発生した場合はログを確認する必要があります。 アプリで除外が必要な場合は、最初に検出したユーザーに応じて、要求をMicrosoft マネージド デスクトップ、または操作を実行できます。

## <a name="initial-deployment-of-apps"></a>アプリの初期展開

アプリを初めて展開する場合、Microsoft マネージド デスクトップの動作を評価する必要があります。 アプリ制御を有効にする正確な手順は、デバイスが環境に既に展開されているかどうかを確認します。

### <a name="devices-not-yet-in-use"></a>まだ使用されていないデバイス

まだデバイスを使用していない場合は、アプリコントロールを有効にMicrosoft マネージド デスクトップを要求するサービス チケットを開きます。 このスケジュールに従って、運用は展開グループにポリシーを段階的に展開します。

|展開グループ  |ポリシーの種類  |Timing  |
|---------|---------|---------|
|テスト     |  監査       |  Day 0       |
|第 1     | Enforced        | 1 日目        |
|高速     | Enforced        |  2 日目       |
|広範な質問     | Enforced        |  3 日目       |

ロールアウト中はいつでも、別のサービス要求を開き、この展開の一部を一時停止またはロールバックできます。

### <a name="devices-already-in-use"></a>既に使用されているデバイス

デバイスが既に 1 つ以上Microsoft マネージド デスクトップ場合は、次の手順を実行します。

1. アプリコントロールを有効にMicrosoft マネージド デスクトップするサービス チケットを開きます。 操作によって、監査ポリシー [がすべてのデバイス](../service-description/app-control.md#audit-policy) に展開されます。
2. [アプリケーションをテストして](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) 、ブロックされるアプリケーションを確認します。 アプリケーションがブロックされる場合は、署名者要求 [を開きます](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)。 
3. テストが完了したら (結果が何であれ)、保留中の署名者要求に気を付け、Operations に通知します。 このスケジュールに従って、運用は展開グループにポリシーを段階的に展開します。

|展開グループ  |ポリシーの種類  |Timing  |
|---------|---------|---------|
|テスト     |  監査       |  Day 0       |
|第 1     | Enforced        | 1 日目        |
|高速     | Enforced        |  要求に応じて一時停止、ロールアウト       |
|広範な質問     | Enforced        |  要求に応じて一時停止、ロールアウト       |

ロールアウト中はいつでも、別のサービス要求を開き、この展開の一部を一時停止またはロールバックできます。



