---
title: Android でのMicrosoft Defender for Endpointに関する問題のトラブルシューティング
description: Android でのMicrosoft Defender for Endpointに関する問題のトラブルシューティング
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, クラウド, 接続, 通信
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 53c04c70291f20ccb23ed54d1de552efb8a7619e
ms.sourcegitcommit: f1b3ecde15e5cbbeadaf51b2cadb6b1d677fc265
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2022
ms.locfileid: "67437770"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Android 上の Microsoft Defender for Endpoint の問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

デバイスのオンボード時に、アプリのインストール後にサインインの問題が表示される場合があります。

オンボード中に、アプリがデバイスにインストールされた後にサインインの問題が発生する可能性があります。

この記事では、サインオンの問題に対処するためのソリューションを提供します。

## <a name="sign-in-failed---unexpected-error"></a>サインインに失敗しました - 予期しないエラー

**サインインに失敗しました:** *予期しないエラーが発生した場合は、後で試してください*

:::image type="content" source="images/f9c3bad127d636c1f150d79814f35d4c.png" alt-text="サインインに失敗したエラー Microsoft Defender 365 ポータルのサインイン ページで予期しないエラーが発生しました。" lightbox="images/f9c3bad127d636c1f150d79814f35d4c.png":::

**メッセージ：**

予期しないエラーが発生した場合は、後で試してください

**原因:**

古いバージョンの "Microsoft Authenticator" アプリがデバイスにインストールされています。

**解決方法:**

Google Play ストアから最新バージョンと [Microsoft Authenticator を](https://play.google.com/store/apps/details?id=com.azure.authenticator) インストールし、もう一度お試しください。

## <a name="sign-in-failed---invalid-license"></a>サインインに失敗しました - ライセンスが無効です

**サインインに失敗しました:** *ライセンスが無効です。管理者にお問い合わせください*

:::image type="content" source="images/920e433f440fa1d3d298e6a2a43d4811.png" alt-text="Microsoft Defender 365 ポータルのサインイン ページのディレクティブ連絡先の詳細" lightbox="images/920e433f440fa1d3d298e6a2a43d4811.png":::

**メッセージ:** *ライセンスが無効です。管理者にお問い合わせください*

**原因:**

Microsoft 365 ライセンスが割り当てられていないか、組織にMicrosoft 365 Enterpriseサブスクリプションのライセンスがありません。

**解決方法:**

ヘルプについては、管理者にお問い合わせください。

## <a name="report-unsafe-site"></a>安全でないサイトを報告する

フィッシング Web サイトは、お客様の個人情報または財務情報を取得する目的で、信頼できる Web サイトを偽装します。 フィッシング サイトである可能性がある Web サイトを報告する場合は、 [ネットワーク保護に関するフィードバックを提供](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) するページにアクセスしてください。

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>一部の OEM デバイスでフィッシング ページがブロックされない

**適用対象:** 特定の OEM のみ

- **小米科技**

Defender for Endpoint for Android によって検出されたフィッシングや有害な Web 脅威は、一部の Intune デバイスではブロックされません。 これらのデバイスでは、次の機能は機能しません。

:::image type="content" source="images/0c04975c74746a5cdb085e1d9386e713.png" alt-text="サイトの安全でない通知メッセージ" lightbox="images/0c04975c74746a5cdb085e1d9386e713.png":::

**原因:**

小米科技デバイスには、新しいアクセス許可モデルが含まれています。 これにより、Defender for Endpoint for Android がバックグラウンドで実行されている間にポップアップ ウィンドウが表示されなくなります。

「バックグラウンドで実行中にポップアップ ウィンドウを表示する」:

:::image type="content" source="images/6e48e7b29daf50afddcc6c8c7d59fd64.png" alt-text="Microsoft Defender 365 ポータルのポップアップ設定ウィンドウ" lightbox="images/6e48e7b29daf50afddcc6c8c7d59fd64.png":::

**解決方法:**

必要なアクセス許可を有効にします。

- バックグラウンドで実行中にポップアップ ウィンドウを表示します。

## <a name="unable-to-allow-permission-for-permanent-protection-during-onboarding-on-some-oem-devices"></a>一部の OEM デバイスでのオンボード中に "永続的な保護" のアクセス許可を許可できない


**適用対象:** 特定の OEM デバイスのみ。

- **小米科技**

Defender アプリは、アプリのオンボードの一環としてデバイスに対するバッテリの最適化/永続的な保護のアクセス許可を要求し、[ **許可]** を選択すると、アクセス許可を設定できなかったというエラーが返されます。 これは、"Permanent Protection" という最後のアクセス許可にのみ影響します。 

**原因:**

Android 11 でバッテリ最適化のアクセス許可が変更されました。 Defender for Endpoint では、バッテリの最適化を無視するようにこの設定を構成することはできません。

**解決方法:**

>[!IMPORTANT]
>この問題は解決されました。 オンボード プロセスを完了するには、最新のアプリ バージョンに更新してください。 問題が解決しない場合は、 **[アプリ内フィードバック](/microsoft-365/security/defender-endpoint/android-support-signin#send-in-app-feedback)** を送信してください。


## <a name="send-in-app-feedback"></a>アプリ内フィードバックを送信する

ユーザーが上記のセクションでまだ対処されていない問題に直面している場合、または一覧表示されている手順を使用して解決できない場合、ユーザーは **診断データ** と共 **にアプリ内フィードバック** を提供できます。 その後、チームはログを調査して適切なソリューションを提供できます。 ユーザーは、次の手順に従って同じ操作を行うことができます。

1. デバイスで **MDE アプリケーション** を開き、左上隅にある **プロファイル アイコン** をクリックします。

    :::image type="content" source="images/select-profile-icon-1.jpg" alt-text="Microsoft Defender for Endpoint ポータルのプロファイル アイコン" lightbox="images/select-profile-icon-1.jpg":::

2. [フィードバックの&ヘルプ] を選択します。

    :::image type="content" source="images/selecthelpandfeedback2.png" alt-text="Microsoft Defender for Endpoint ポータルで選択できるフィードバック オプション&ヘルプ" lightbox="images/selecthelpandfeedback2.png":::

3. [Microsoft にフィードバックを送信する] を選択します。

    :::image type="content" alt-text="Microsoft にフィードバックを送信するを選択する" source="images/send-feedback-to-microsoft-3.jpg":::

4. 指定したオプションから選択します。 問題を報告するには、[問題を報告する] を選択します。

    :::image type="content" source="images/report-issue-4.jpg" alt-text="[問題を報告する] オプション" lightbox="images/report-issue-4.jpg":::

5. 発生している問題の詳細を入力し、[診断データの送信] をオンにします。 チームがソリューションまたはフォローアップで連絡できるように、[メール アドレスを含める] をオンにすることをお勧めします。

    :::image type="content" source="images/finalsubmit5.png" alt-text="詳細を追加して診断データを添付できるウィンドウ" lightbox="images/finalsubmit5.png":::

6. [送信] をクリックして、フィードバックを正常に送信します。

