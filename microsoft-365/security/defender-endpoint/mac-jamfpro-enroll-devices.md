---
title: MacOS デバイス上の Microsoft Defender for Endpoint を Jamf Pro
description: MacOS デバイス上の Microsoft Defender for Endpoint を Jamf Pro
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6189b61826cd56e2a8652032998c3b2df8f980ce
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468679"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a>MacOS デバイス上の Microsoft Defender for Endpoint を Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a>macOS デバイスの登録

JamF に登録するには、複数の方法があります。

この記事では、次の 2 つの方法について説明します。

- [方法 1: 登録の招待](#enrollment-method-1-enrollment-invitations)
- [方法 2: 事前登録](#enrollment-method-2-prestage-enrollments)

完全な一覧については、「コンピューターの登録 [について」を参照してください](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)。

## <a name="enrollment-method-1-enrollment-invitations"></a>登録方法 1: 登録の招待

1. [Jamf Pro] ダッシュボードで、[登録の招待 **] に移動します**。

   :::image type="content" source="images/a347307458d6a9bbfa88df7dbe15398f.png" alt-text="構成設定1" lightbox="images/a347307458d6a9bbfa88df7dbe15398f.png":::

2. [ **+ 新規] を選択します**。

   :::image type="content" source="images/b6c7ad56d50f497c38fc14c1e315456c.png" alt-text="ロゴの説明が自動的に生成される閉じる" lightbox="images/b6c7ad56d50f497c38fc14c1e315456c.png":::

3. [ **招待の受信者の指定] >** **[** 電子メール アドレス] の下に、受信者の電子メール アドレスを入力します。

    :::image type="content" source="images/718b9d609f9f77c8b13ba88c4c0abe5d.png" alt-text="構成設定 2" lightbox="images/718b9d609f9f77c8b13ba88c4c0abe5d.png":::

    :::image type="content" source="images/ae3597247b6bc7c5347cf56ab1e820c0.png" alt-text="構成設定3" lightbox="images/ae3597247b6bc7c5347cf56ab1e820c0.png":::

    たとえば、次の janedoe@contoso.com

    :::image type="content" source="images/4922c0fcdde4c7f73242b13bf5e35c19.png" alt-text="構成設定4" lightbox="images/4922c0fcdde4c7f73242b13bf5e35c19.png":::

4. 招待のメッセージを構成します。

   :::image type="content" source="images/ce580aec080512d44a37ff8e82e5c2ac.png" alt-text="構成設定5" lightbox="images/ce580aec080512d44a37ff8e82e5c2ac.png":::

   :::image type="content" source="images/5856b765a6ce677caacb130ca36b1a62.png" alt-text="構成設定6" lightbox="images/5856b765a6ce677caacb130ca36b1a62.png":::

   :::image type="content" source="images/3ced5383a6be788486d89d407d042f28.png" alt-text="構成設定7" lightbox="images/3ced5383a6be788486d89d407d042f28.png":::

   :::image type="content" source="images/54be9c6ed5b24cebe628dc3cd9ca4089.png" alt-text="構成設定8" lightbox="images/54be9c6ed5b24cebe628dc3cd9ca4089.png":::

## <a name="enrollment-method-2-prestage-enrollments"></a>登録方法 2: 事前登録

1. Jamf Proで、[**Prestage 登録] に移動します**。

   :::image type="content" source="images/6fd0cb2bbb0e60a623829c91fd0826ab.png" alt-text="構成設定9" lightbox="images/6fd0cb2bbb0e60a623829c91fd0826ab.png":::

2. 「Computer [PreStage 登録」の手順に従います](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html)。

## <a name="enroll-macos-device"></a>macOS デバイスの登録

1. [ **続行] を** 選択し、[システムの基本設定] ウィンドウから **CA 証明書をインストール** します。

   :::image type="content" source="images/jamfpro-ca-certificate.png" alt-text="Jamf Pro登録 1" lightbox="images/jamfpro-ca-certificate.png":::

2. CA 証明書がインストールされた後、ブラウザー ウィンドウに戻り、[続行] を **選択して** MDM プロファイルをインストールします。

   :::image type="content" source="images/jamfpro-install-mdm-profile.png" alt-text="Jamf Pro登録 2" lightbox="images/jamfpro-install-mdm-profile.png":::

3. [JAMF **からの** ダウンロードを許可する] を選択します。

   :::image type="content" source="images/jamfpro-download.png" alt-text="Jamf Pro登録3" lightbox="images/jamfpro-download.png":::

4. [続行 **] を** 選択して MDM プロファイルのインストールを続行します。

   :::image type="content" source="images/jamfpro-install-mdm.png" alt-text="Jamf Pro登録 4" lightbox="images/jamfpro-install-mdm.png":::

5. [続行 **] を** 選択して MDM プロファイルをインストールします。

   :::image type="content" source="images/jamfpro-mdm-unverified.png" alt-text="Jamf Pro登録5" lightbox="images/jamfpro-mdm-unverified.png":::

6. [続行 **] を**  選択して構成を完了します。

   :::image type="content" source="images/jamfpro-mdm-profile.png" alt-text="Jamf Pro登録 6" lightbox="images/jamfpro-mdm-profile.png":::
