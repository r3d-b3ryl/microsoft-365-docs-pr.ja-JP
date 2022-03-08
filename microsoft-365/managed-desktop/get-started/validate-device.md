---
title: 新しいデバイスを検証する
description: デバイスを注文する前に、各モデルの 1 つを取得してテストします。
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: aed391128d0a7bfdd3b6a97c9cc661267b867820
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63322283"
---
# <a name="validate-new-devices"></a>新しいデバイスを検証する

Microsoft Managed Desktop を初めて使用する場合でも、長時間購読している場合でも、サービスに初めて登録するデバイス モデルの例をテストする必要があります。 これは、新しいデバイスを注文する場合でも、Microsoft Managed Desktop に推奨されるデバイスを含む既存のデバイスを再利用する場合にも当てはまる。

## <a name="view-devices"></a>デバイスの表示

**サービスで使用するために推奨されるデバイスを表示するには、次のコマンドを実行します。**

1. [ビジネス [デバイス サイトWindows Pro] に移動](https://www.microsoft.com/en-us/windowsforbusiness/view-all-devices)します。
1. 左側の **ウィンドウの [** フィルター] セクションで、[機能] フィルター **を展開** します。
1. [ **Microsoft Managed Desktop] を選択します**。

デバイスを検証すると、期待するユーザー エクスペリエンスが確実に提供されます。

## <a name="validate-devices"></a>デバイスの検証

**デバイスを検証するには、**

1. 次の記事の手順に従って、新しいモデルの 1 つ以上の例を実行します。
    - [デバイスの準備](prepare-devices.md)
    - [ユーザー エクスペリエンスをローカライズ](localization.md)
    - [Autopilot と登録ステータス ページの初回実行時エクスペリエンス](esp-first-run.md)
    - [Windows 10 の位置情報サービス](device-location.md)
    - [アプリ制御の使用を開始する](get-started-app-control.md)
    - [アプリをデバイスに展開する](deploy-apps.md)
2. 次のエクスペリエンスがエラー、エラー、またはプロンプトなしで動作するように確認します。
    - ネットワークに参加し、ユーザーがサインインした後の自動パイロット エクスペリエンス。
    - [登録の状態] ページ [を有効にしている場合](esp-first-run.md)は、機能します。
    - ユーザーは、アプリケーションにサインインOfficeできます。
    - OneDriveデスクトップ、ドキュメント、ピクチャなどのWindowsフォルダーが同期されます。
    - デバイスは、更新プログラム、ポリシー、および業務行アプリケーションを受信します。
3. デバイス インベントリ レポートで報告されたデバイスとハードウェア要件を確認 [して](../working-with-managed-desktop/device-inventory-report.md) 、期待したデバイスと一致していることを確認します。

問題が発生した場合は、管理 [ポータルでサポート](../working-with-managed-desktop/admin-support.md) を要求できます。

すべてがうまくいった場合は、展開に必要な検証済みデバイスの残りの部分を注文する準備が整いました。
