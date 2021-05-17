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
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430461"
---
# <a name="get-started-with-app-control"></a>アプリ制御の使用を開始する

環境でアプリ制御を有効にする前に [、Microsoft Managed Desktop](../service-description/app-control.md) がどのようにアプリを実装し、役割と責任を果たしたのか、必ず確認して理解してください。

Microsoft Managed Desktop は、セキュリティで保護された基本ポリシーを取得するより困難な側面に注意を引き付け、アプリの制御を簡素化します。 IT 管理者は、テスト リングでアプリをテストし、警告やエラーが発生した場合はログを確認する必要があります。 アプリで除外が必要な場合は、要求を申請するか、Microsoft Managed Desktop 操作を実行できます (最初に検出したユーザーに応じて)。

## <a name="initial-deployment-of-apps"></a>アプリの初期展開

アプリを初めて展開する場合、Microsoft Managed Desktop は現在の動作を評価する必要があります。 アプリ制御を有効にする正確な手順は、デバイスが環境に既に展開されているかどうかを確認します。

### <a name="devices-not-yet-in-use"></a>まだ使用されていないデバイス

デバイスがまだ使用されていない場合は、Microsoft Managed Desktop Operations でサービス チケットを開き、アプリコントロールを有効にしてください。 このスケジュールに従って、運用は展開グループにポリシーを段階的に展開します。

|展開グループ  |ポリシーの種類  |Timing  |
|---------|---------|---------|
|テスト     |  監査       |  Day 0       |
|第 1     | Enforced        | 1 日目        |
|高速     | Enforced        |  2 日目       |
|広範な質問     | Enforced        |  3 日目       |

ロールアウト中はいつでも、別のサービス要求を開き、この展開の一部を一時停止またはロールバックできます。

### <a name="devices-already-in-use"></a>既に使用されているデバイス

少なくとも 1 つの Microsoft Managed Desktop デバイスが既に使用されている場合は、次の手順を実行します。

1. Microsoft Managed Desktop Operations でサービス チケットを開き、アプリコントロールを有効にしてください。 操作によって、監査ポリシー [がすべてのデバイス](../service-description/app-control.md#audit-policy) に展開されます。
2. [アプリケーションをテストして](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) 、ブロックされるアプリケーションを確認します。 アプリケーションがブロックされる場合は、署名者要求 [を開きます](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)。 
3. テストが完了したら (結果が何であれ)、保留中の署名者要求に気を付け、Operations に通知します。 このスケジュールに従って、運用は展開グループにポリシーを段階的に展開します。

|展開グループ  |ポリシーの種類  |Timing  |
|---------|---------|---------|
|テスト     |  監査       |  Day 0       |
|第 1     | Enforced        | 1 日目        |
|高速     | Enforced        |  要求に応じて一時停止、ロールアウト       |
|広範な質問     | Enforced        |  要求に応じて一時停止、ロールアウト       |

ロールアウト中はいつでも、別のサービス要求を開き、この展開の一部を一時停止またはロールバックできます。



