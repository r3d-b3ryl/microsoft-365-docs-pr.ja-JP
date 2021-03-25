---
title: Android 用 Microsoft Defender ATP の問題のトラブルシューティング
description: Android 用 Microsoft Defender ATP の問題のトラブルシューティング
keywords: microsoft、Defender、atp、android、クラウド、接続、コミュニケーション
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 444541c85f8f4416288dcebf4bbee2c65a33d3d2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164871"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-for-android"></a>Microsoft Defender for Endpoint for Android の問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

デバイスのオンボード時に、アプリのインストール後にサインインの問題が表示される場合があります。

オンボーディング中に、アプリがデバイスにインストールされた後にサインインの問題が発生する可能性があります。

この記事では、サインオンの問題に対処するためのソリューションを提供します。  

## <a name="sign-in-failed---unexpected-error"></a>サインインに失敗しました - 予期しないエラー
**サインインに失敗しました: 予期しない***エラーが発生した場合は、後で試してください*

![サインインに失敗したエラーのイメージ 予期しないエラー](images/f9c3bad127d636c1f150d79814f35d4c.png)

**メッセージ：**

予期しないエラー、後で試す

**原因:**

デバイスに古いバージョンの "Microsoft Authenticator" アプリがインストールされています。

**解決方法:**

Google Play ストアから最新バージョンの [Microsoft Authenticator を](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) インストールし、もう一度やり直す

## <a name="sign-in-failed---invalid-license"></a>サインインに失敗しました - 無効なライセンス

**サインインに失敗しました:** *ライセンスが無効です。管理者に問い合わせてください*

![サインインに失敗したイメージは、管理者に問い合わせてください](images/920e433f440fa1d3d298e6a2a43d4811.png)

**メッセージ:** *無効なライセンス、管理者に問い合わせてください*

**原因:**

Microsoft 365 ライセンスが割り当てられていないか、組織に Microsoft 365 Enterprise サブスクリプションのライセンスが割り当てられていない。

**解決方法:**

ヘルプについては、管理者に問い合わせてください。

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>一部の OEM デバイスでフィッシング ページがブロックされない

**適用対象:** 特定の OEM のみ

-   **Xiaomi**

Android 用 Defender for Endpoint によって検出されるフィッシングや有害な Web の脅威は、一部の Xiaomi デバイスではブロックされません。 次の機能は、これらのデバイスでは機能しません。

![安全でないと報告されたサイトの画像](images/0c04975c74746a5cdb085e1d9386e713.png)


**原因:**

Xiaomi デバイスには、新しいアクセス許可モデルが含まれます。 これにより、Defender for Endpoint for Android では、バックグラウンドで実行されている間にポップアップ ウィンドウが表示されなかっています。

Xiaomi デバイスのアクセス許可: "バックグラウンドで実行中にポップアップ ウィンドウを表示する"

![ポップアップ設定のイメージ](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

**解決方法:**

Xiaomi デバイスで必要なアクセス許可を有効にします。

- バックグラウンドで実行中にポップアップ ウィンドウを表示します。
