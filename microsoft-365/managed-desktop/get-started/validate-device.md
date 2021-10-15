---
title: 新しいデバイスを検証する
description: デバイスを注文する前に、各モデルの 1 つを取得してテストします。
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 2b3ba016e5a205ddb6eaccc4df71bdc4ad612085
ms.sourcegitcommit: 317fab13e84b2867087a6ba0a593313ecf43bbed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2021
ms.locfileid: "60364617"
---
# <a name="validate-new-devices"></a>新しいデバイスを検証する

Microsoft Managed Desktop を初めて使用する場合でも、長時間の購読者の場合も、サービスに初めて登録するデバイス モデルの例をテストする必要があります。 これは、新しいデバイスを注文する場合でも、既存のデバイスを再利用する場合でも当てはめ、ビジネス デバイス サイトの Microsoft Managed Desktop に推奨されるデバイスも[含Windows Proです](https://www.microsoft.com/en-us/windowsforbusiness/view-all-devices)。 そのサイトで、[フィルター] 領域で [機能] を展開し **、[Microsoft Managed Desktop]** を選択して、サービスで使用する推奨デバイスを表示します。 デバイスを検証すると、期待するユーザー エクスペリエンスが確実に提供されます。

## <a name="validate-devices"></a>デバイスの検証

1. 次の記事の手順に従って、新しいモデルの 1 つ以上の例を実行します。
    - [Microsoft マネージド デスクトップのデバイスをセットアップする](set-up-devices.md)
    - [ユーザー エクスペリエンスをローカライズ](localization.md)
    - [Autopilot と登録ステータス ページの初回実行時エクスペリエンス](esp-first-run.md)
    - [Windows 10 の位置情報サービス](device-location.md)
    - [アプリコントロールの使用を開始する](get-started-app-control.md)
    - [アプリをデバイスに展開する](deploy-apps.md)
2. 次のエクスペリエンスがエラー、エラー、またはプロンプトなしで動作するように確認します。
    - ネットワークに参加してユーザーがサインインした後の自動パイロット エクスペリエンス
    - [登録の状態] ページ [を有効にしている場合](esp-first-run.md)は、機能します。
    - ユーザーは、アプリケーションにサインインOfficeできます
    - OneDriveデスクトップ、ドキュメント、ピクチャなどのWindowsフォルダーの同期
    - デバイスが更新プログラム、ポリシー、および業務アプリケーションを受け取る
3. デバイス インベントリ レポートで報告されたデバイスとハードウェア要件を確認 [して](../working-with-managed-desktop/device-inventory-report.md) 、期待したデバイスと一致していることを確認します。

問題が発生した場合は、管理 [ポータルでサポート](../working-with-managed-desktop/admin-support.md) を要求できます。

すべてがうまくいった場合は、展開に必要な検証済みデバイスの残りの部分を注文する準備が整いました。
