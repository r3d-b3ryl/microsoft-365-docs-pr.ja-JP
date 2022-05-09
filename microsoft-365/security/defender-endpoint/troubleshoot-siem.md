---
title: Microsoft Defender for Endpointでの SIEM ツール統合の問題のトラブルシューティング
description: MICROSOFT DEFENDER FOR ENDPOINTで SIEM ツールを使用するときに発生する可能性がある問題のトラブルシューティングを行います。
keywords: トラブルシューティング, siem, クライアント シークレット, シークレット
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: b6ed0342183734d9b4feb1c20a6c4059b77e64d6
ms.sourcegitcommit: 986ea76ecaceb5fe6b9616e553003e3c5b0df2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2022
ms.locfileid: "62213993"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a>SIEM ツール統合に関する問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

SIEM ツールで検出をプルするときに、問題のトラブルシューティングが必要になる場合があります。

このページでは、発生する可能性のある問題をトラブルシューティングするための詳細な手順について説明します。

## <a name="learn-how-to-get-a-new-client-secret"></a>新しいクライアント シークレットを取得する方法について説明します

クライアント シークレットの有効期限が切れた場合、または SIEM ツール アプリケーションを有効にしているときに提供されたコピーを間違えた場合は、新しいシークレットを取得する必要があります。

1. [Azure 管理ポータル](https://portal.azure.com)にログインします。

2. **Azure Active Directory** を選択します。

3. テナントを選択します。

4. **[アプリの登録**] をクリックします。 次に、アプリケーションの一覧でアプリケーションを選択します。

5. [ **証明書&シークレット** ] セクションを選択し、[新しいクライアント シークレット] をクリックして説明を入力し、有効期間を指定します。

6. [**保存**] をクリックします。 キー値が表示されます。

7. 値をコピーし、安全な場所に保存します。

## <a name="error-when-getting-a-refresh-access-token"></a>更新アクセス トークンを取得するときのエラー

脅威インテリジェンス API または SIEM ツールを使用しているときに更新トークンを取得しようとしたときにエラーが発生した場合は、関連するアプリケーションの応答 URL をAzure Active Directoryに追加する必要があります。

1. [Azure 管理ポータル](https://ms.portal.azure.com)にログインします。

2. **Azure Active Directory** を選択します。

3. テナントを選択します。

4. [ **アプリの登録]** をクリックします。 次に、アプリケーションの一覧でアプリケーションを選択します。

5. 次の URL を追加します。
   - 欧州連合の場合: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`
   - 英国の場合: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`
   - 米国の場合: `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.

6. [**保存**] をクリックします。

## <a name="error-while-enabling-the-siem-connector-application"></a>SIEM コネクタ アプリケーションを有効にしているときにエラーが発生しました

SIEM コネクタ アプリケーションを有効にしようとしたときにエラーが発生した場合は、ブラウザーのポップアップ ブロック設定を確認します。 機能を有効にすると、開かれている新しいウィンドウがブロックされている可能性があります。

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troubleshootsiem-belowfoldlink)

## <a name="related-topics"></a>関連項目

- [SIEM ツールへのプル検出](configure-siem.md)

