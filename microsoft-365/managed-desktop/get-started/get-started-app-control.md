---
title: アプリ制御の使用を開始する
description: この記事では、アプリコントロールを有効にする方法について説明します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
---

# <a name="get-started-with-app-control"></a>アプリ制御の使用を開始する

環境でアプリ制御を有効にする前に、 [Microsoft Managed Desktop](../service-description/app-control.md) がどのようにアプリを実装し、役割と責任を果たしたのか、必ず確認して理解してください。

Microsoft Managed Desktop は、セキュリティで保護された基本ポリシーを取得するより困難な側面に注意を引き付け、アプリの制御を簡素化します。

IT 管理者は、テスト リングでアプリをテストし、警告やエラーのログを確認する必要があります。 アプリで除外が必要な場合は、要求を申請するか、Microsoft Managed Desktop 操作を実行できます (最初に検出したユーザーに応じて)。

## <a name="initial-deployment-of-apps"></a>アプリの初期展開

アプリを初めて展開する場合、Microsoft Managed Desktop は現在の動作を評価する必要があります。 アプリ制御を有効にする正確な手順は、デバイスが環境に既に展開されているかどうかを確認します。

### <a name="devices-not-yet-in-use"></a>まだ使用されていないデバイス

デバイスがまだ使用されていない場合は、Microsoft Managed Desktop Operations でサポート チケットを開き、アプリコントロールの有効を要求します。 このスケジュールに従って、運用は展開グループにポリシーを段階的に展開します。

| 展開グループ | ポリシーの種類 | Timing |
| ------ | ------ | ------ |
| テスト |  監査 |  Day 0 |
| 第 1 | Enforced | 1 日目 |
| 高速 | Enforced |  2 日目 |
| 広範な質問 | Enforced |  3 日目 |

ロールアウト中にいつでも、この展開の一部を一時停止またはロールバックする別のサポート要求をいつでも開きます。

### <a name="devices-already-in-use"></a>既に使用されているデバイス

少なくとも 1 つの Microsoft Managed Desktop デバイスが既に使用されている場合は、次の手順を実行します。

1. Microsoft Managed Desktop Operations でサービス チケットを開き、アプリコントロールを有効にしてください。 操作によって、監査ポリシー [がすべてのデバイス](../service-description/app-control.md#audit-policy) に展開されます。
2. [アプリケーションをテストして](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) 、ブロックされるアプリケーションを確認します。 アプリケーションがブロックされる場合は、署名者 [要求を開きます](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)。
3. テストが完了したら (結果が何であれ)、保留中の署名者要求に気を付け、Operations に通知します。 このスケジュールに従って、運用は展開グループにポリシーを段階的に展開します。

| 展開グループ | ポリシーの種類 | Timing |
| ------ | ------ | ------ |
| テスト     | 監査 |  Day 0 |
| 第 1     | Enforced | 1 日目 |
| 高速     | Enforced |  要求に応じて一時停止、ロールアウト |
| 広範な質問     | Enforced |  要求に応じて一時停止、ロールアウト |

ロールアウト中にいつでも、この展開の一部を一時停止またはロールバックする別のサポート要求をいつでも開きます。

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop の使用を開始する手順

1. [管理ポータル](access-admin-portal.md)にアクセスします。
1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)。
1. [登録後に設定を調整する](conditional-access.md)。
1. [Intune ポータル サイト](company-portal.md)を展開して割り当てます。
1. [ライセンスを割り当てる](assign-licenses.md)。
1. [アプリを展開する](deploy-apps.md)。
1. [デバイスをセットアップする](set-up-devices.md)。
1. [Autopilot と登録ステータス ページの初回実行時エクスペリエンス](esp-first-run.md)のセットアップ。
1. [ユーザー サポート機能を有効にする](enable-support.md)。
1. [ユーザーがデバイスを使えるようにする](get-started-devices.md)。
1. アプリ コントロールの使用を開始します (この記事)。
