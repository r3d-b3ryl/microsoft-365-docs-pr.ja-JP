---
title: 新しいデバイスを検証する
description: デバイスを注文する前に、各モデルの 1 つを取得してテストします。
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 1654998a69b364ebf399c2aabac185bc98fb9388
ms.sourcegitcommit: be83f1222c30ffa8202c19a2797cc755fc3b72af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/17/2021
ms.locfileid: "58372834"
---
# <a name="validate-new-devices"></a>新しいデバイスを検証する

Microsoft マネージド デスクトップ を初めて使用する場合でも、長時間の購読者でも、サービスに初めて登録するデバイス モデルの例をテストしてください。 これは、ブランドの新しいデバイスを注文する場合でも、既存のデバイスを再利用する場合でも当てはめ、ビジネス デバイス サイトの shop Microsoft マネージド デスクトップに推奨Windows 10 Proデバイスを含むデバイスも[含](https://www.microsoft.com/en-us/windowsforbusiness/view-all-devices)めて有効です。 そのサイトで、[フィルター] 領域で [機能] を展開し、[サービス] を選択して、サービスで使用する推奨 **デバイスMicrosoft マネージド デスクトップ。** デバイスを検証すると、期待するユーザー エクスペリエンスが確実に提供されます。

## <a name="validate-devices"></a>デバイスの検証

1. 次の記事の手順に従って、新しいモデルの 1 つ以上の例を実行します。
    - [Microsoft マネージド デスクトップのデバイスをセットアップする](set-up-devices.md)
    - [ユーザー エクスペリエンスをローカライズ](localization.md)
    - [Autopilot と登録ステータス ページの初回実行時エクスペリエンス](esp-first-run.md)
    - [Windows 10 の位置情報サービス](device-location.md)
    - [アプリ制御の使用を開始する](get-started-app-control.md)
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
