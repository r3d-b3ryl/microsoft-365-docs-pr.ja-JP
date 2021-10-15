---
title: iOS 機能に Microsoft Defender for Endpoint を展開する
description: 登録されていない iOS デバイスに Microsoft Defender for Endpoint を展開する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, ios, configure, features, ios
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: sunasing
author: sunasing
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f5743cecab5e6a1bd0ab51b5a984a49e04f80184
ms.sourcegitcommit: 1e990628d72b6d392500ea564859543e7c8bc632
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2021
ms.locfileid: "60386210"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-unenrolled-ios-devices"></a>登録されていない iOS デバイスに Microsoft Defender for Endpoint を展開する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> iOS のエンドポイントの Defender は、Web 保護機能を提供するために VPN を使用します。 これは通常の VPN ではなく、デバイス外のトラフィックを受け取らないローカル/自己ループ VPN です。

## <a name="configure-microsoft-defender-for-endpoint-risk-signals-in-app-protection-policy-mam"></a>アプリ保護ポリシー (MAM) で Microsoft Defender for Endpoint リスクシグナルを構成する

モバイル デバイス管理 (MDM) シナリオでエンタープライズ ユーザーを既に保護している Android 上の Microsoft Defender for Endpoint は、Intune モバイル デバイス管理 (MDM) を使用して登録されていないデバイスのモバイル アプリ管理 (MAM) のサポートを拡張しました。 また、このサポートは、他のエンタープライズ モビリティ管理ソリューションを使用しているお客様にも拡張しますが、モバイル アプリケーション管理 (MAM) には Intune を使用します。この機能を使用すると、アプリケーション内で組織のデータを管理および保護できます。

Microsoft Defender for Endpoint on Android の脅威情報は、Intune アプリ保護ポリシーによってこれらのアプリを保護するために活用されます。 アプリ保護ポリシー (APP) は、組織のデータを安全に保つか、管理アプリに含まれるか確認するルールです。 管理アプリケーションにはアプリ保護ポリシーが適用され、Intune で管理できます。  

Android 上のエンドポイント用 Microsoft Defender は、MAM の両方の構成をサポートしています
- **Intune MDM + MAM**: IT 管理者は、Intune モバイル デバイス管理 (MDM) に登録されているデバイスでアプリ保護ポリシーを使用してアプリのみを管理できます。
- **デバイス登録なしの** MAM : デバイス登録なしの MAM、または MAM-WE を使用すると [](/mem/intune/app/app-protection-policy)、IT 管理者は Intune MDM に登録されていないデバイスでアプリ保護ポリシーを使用してアプリを管理できます。 つまり、サードパーティの EMM プロバイダーに登録されているデバイスでは、Intune によってアプリを管理できます。 上記の両方の構成を使用してアプリを管理するには、管理者センターで Intune[をMicrosoft エンドポイント マネージャーする必要があります。](https://go.microsoft.com/fwlink/?linkid=2109431)

この機能を有効にするには、管理者が Microsoft Defender for Endpoint と Intune 間の接続を構成し、アプリ保護ポリシーを作成し、対象のデバイスとアプリケーションにポリシーを適用する必要があります。 
 
エンド ユーザーは、デバイスに Microsoft Defender for Endpoint をインストールし、オンボーディング フローをアクティブ化するための手順を実行する必要があります。

### <a name="pre-requisites"></a>前提条件

1. **コネクタが有効になっているか確認します**。 <br> 統合セキュリティ [コンソールで](https://security.microsoft.com)、[エンドポイントの高度な **機能** 設定に移動し、接続が有効Microsoft Intune  >    >  **確認** します。

  ![Defender for Endpoint -Intune コネクタのイメージ](images/enable-intune-connection.png)
  
2. **Intune ポータルでコネクタが有効になっているか確認します**。 <br> [Microsoft Endpoint manager 管理センターで、[](https://go.microsoft.com/fwlink/?linkid=2109431)エンドポイント セキュリティ] [エンドポイント用 Microsoft Defender] に移動し、[接続] 状態  >  が有効になっているか確認します。

  ![アプリの設定](images/app-settings.png)

### <a name="create-an-app-protection-policy"></a>アプリ保護ポリシーを作成する
 
アプリ保護ポリシーを作成して、Microsoft Defender for Endpoint リスクシグナルに基づいて管理アプリのデータへのアクセスをブロックまたはワイプします。
Microsoft Defender for Endpoint は、アプリ保護ポリシー (APP、 MAM とも呼ばれる) で使用される脅威信号を送信するように構成できます。 この機能を使用すると、Microsoft Defender for Endpoint を使用して管理対象アプリを保護できます。

1. ポリシーを作成する <br>
アプリ保護ポリシー (APP) は、組織のデータを安全に保つか、管理アプリに含まれるか確認するルールです。 ポリシーには、ユーザーが "企業" データにアクセスまたは移動しようとするときに適用されるルール、またはユーザーがアプリ内に入っているときに禁止または監視される一連のアクションを指定できます。 

![ポリシー作成のイメージ](images/create-policy.png)

2. アプリを追加する <br>
    a. このポリシーをさまざまなデバイス上のアプリに適用する方法を選択します。 次に、少なくとも 1 つのアプリを追加します。 <br>
    このポリシーが管理されていないデバイスに適用されるかどうかを指定するには、このオプションを使用します。 また、任意の管理状態のデバイス上のアプリにポリシーをターゲットにすることもできます。
モバイル アプリの管理ではデバイス管理が必要ではないので、管理デバイスと管理されていないデバイスの両方で会社のデータを保護できます。 管理はユーザー ID を中心とします。デバイス管理の要件は削除されます。 企業は、MDM を使用する場合と使用しない場合でも、アプリ保護ポリシーを同時に使用できます。 たとえば、会社が発行した電話と自分の個人用タブレットの両方を使用する従業員を考えます。 会社の電話は MDM に登録され、アプリ保護ポリシーによって保護され、個人用デバイスはアプリ保護ポリシーでのみ保護されます。

    b. [アプリの選択]<br>
    管理アプリは、アプリ保護ポリシーが適用され、Intune で管理できるアプリです。 [Intune SDK](/mem/intune/developer/app-sdk)に統合されたアプリ、または Intune アプリによってラップされたアプリは、Intune アプリ[App Wrapping Tool](/mem/intune/developer/apps-prepare-mobile-application-management)ポリシーを使用して管理できます。 これらのツールを使用して[構築](/mem/intune/apps/apps-supported-intune-apps)Microsoft Intune、パブリックに使用できる保護されたアプリの公式リストを参照してください。

    *例: Outlookアプリとして使用する*

    ![管理Outlookイメージ](images/managed-app.png)

 3. 保護ポリシーのサインイン セキュリティ要件を設定します。 <br>
[ **デバイスの条件>最大許容** デバイス脅威レベルの設定] を選択 **し、値** を入力します。 次に、[  **アクション] を選択します。[アクセスをブロックする] を選択します**。 Android 上のエンドポイント用 Microsoft Defender は、このデバイス脅威レベルを共有します。

    ![条件付き起動のイメージ](images/conditional-launch.png)

4. ポリシーを適用する必要があるユーザー グループを割り当てる。<br>
  [含 **まれるグループ] を選択します**。 次に、関連するグループを追加します。 


MAM またはアプリ保護ポリシーの詳細については [、「iOS アプリ保護ポリシー設定」を参照してください](/mem/intune/apps/app-protection-policy-settings-ios)。

## <a name="deploy-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>MICROSOFT Defender for Endpoint for MAM または登録されていないデバイスに展開する

Microsoft Defender for Endpoint on iOS では、アプリ保護ポリシーのシナリオを有効にし、Apple アプリ ストアで利用できます。

アプリ保護ポリシーが、Microsoft Defender for Endpoint からのデバイス リスク信号を含むアプリ用に構成されている場合、そのようなアプリを使用する場合、ユーザーは Microsoft Defender for Endpoint をインストールするようにリダイレクトされます。 また、ユーザーは Apple アプリ ストアから直接アプリの最新バージョンをインストールすることもできます。
