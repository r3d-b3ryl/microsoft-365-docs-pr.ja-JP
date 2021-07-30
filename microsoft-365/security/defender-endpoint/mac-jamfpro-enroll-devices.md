---
title: MacOS デバイス上の Microsoft Defender for Endpoint を Jamf デバイスに登録Pro
description: MacOS デバイス上の Microsoft Defender for Endpoint を Jamf デバイスに登録Pro
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3907c52e4cae7dedba38c893ee34b0b857316d08
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53652025"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a>MacOS デバイス上の Microsoft Defender for Endpoint を Jamf デバイスに登録Pro 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a>macOS デバイスの登録

JamF に登録するには、複数の方法があります。

この記事では、次の 2 つの方法について説明します。

- [方法 1: 登録の招待](#enrollment-method-1-enrollment-invitations)
- [方法 2: 事前登録](#enrollment-method-2-prestage-enrollments)

完全な一覧については、「コンピューターの登録 [について」を参照してください](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)。


## <a name="enrollment-method-1-enrollment-invitations"></a>登録方法 1: 登録の招待

1. Jamf Proで、[登録の招待]**に移動します**。

    ![構成設定のイメージ1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. [+ **新規] を選択します**。

    ![ロゴの説明が自動的に生成される](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. [ **招待の受信者の指定] >** **[** 電子メール アドレス] の下に、受信者の電子メール アドレスを入力します。

    ![構成設定のイメージ2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![構成設定のイメージ 3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    たとえば、次の janedoe@contoso.com

    ![構成設定のイメージ 4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. 招待のメッセージを構成します。

    ![構成設定のイメージ5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![構成設定のイメージ6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![構成設定のイメージ 7](images/3ced5383a6be788486d89d407d042f28.png)

    ![構成設定のイメージ8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a>登録方法 2: 事前登録

1. Jamf Proで **、[Prestage 登録] に移動します**。

    ![構成設定のイメージ 9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. 「Computer [PreStage 登録」の手順に従います](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html)。

## <a name="enroll-macos-device"></a>macOS デバイスの登録

1. [ **続行] を** 選択し、[システムの基本設定] ウィンドウから **CA 証明書をインストール** します。

    ![Jamf の登録Pro 1](images/jamfpro-ca-certificate.png)

2. CA 証明書がインストールされた後、ブラウザー ウィンドウに戻り、[続行] を **選択して** MDM プロファイルをインストールします。 

    ![Jamf の登録Pro 2](images/jamfpro-install-mdm-profile.png)

3. [JAMF **からの** ダウンロードを許可する] を選択します。

    ![Jamf の登録Pro 3](images/jamfpro-download.png)

4. [続行 **] を** 選択して MDM プロファイルのインストールを続行します。 

    ![Jamf ファイルの登録Pro 4](images/jamfpro-install-mdm.png)

5. [続行 **] を** 選択して MDM プロファイルをインストールします。

    ![Jamf の登録Pro 5](images/jamfpro-mdm-unverified.png)

6. [続行 **] を**  選択して構成を完了します。 

    ![Jamf ファイルの登録Pro 6](images/jamfpro-mdm-profile.png)
