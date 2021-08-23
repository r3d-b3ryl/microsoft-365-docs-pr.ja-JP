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
ms.openlocfilehash: 83681c2258a140c4e7bc4757e0d4f9f63c9991db
ms.sourcegitcommit: 00a8a3376ea02770143af9a80cbe17a2b62636e3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2021
ms.locfileid: "58364591"
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

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>データの使用を開始するMicrosoft マネージド デスクトップ

1. 管理 [ポータルにアクセスします](access-admin-portal.md)。
1. [管理者ポータルで管理者連絡先を追加して確認します](add-admin-contacts.md)。
1. [登録後に設定を調整します](conditional-access.md)。
1. ユーザーを展開して割[り当Intune ポータル サイト](company-portal.md)します。
1. [ライセンスを割り当てる](assign-licenses.md)。
1. [アプリを展開します](deploy-apps.md)。
1. [デバイスをセットアップします](set-up-devices.md)。
1. Autopilot と [登録の状態] ページ [を使用して、初回実行エクスペリエンスを設定します](esp-first-run.md)。
1. [ユーザー サポート機能を有効にする](enable-support.md)。
1. [ユーザーがデバイスを使用する準備を整えます](get-started-devices.md)。
1. アプリ コントロールの使用を開始します (この記事)。

