---
title: iOS機能にMicrosoft Defender for Endpointをデプロイする
description: 登録されていないiOS デバイスにMicrosoft Defender for Endpointを展開する方法について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, configure, features, ios
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
ms.openlocfilehash: 1d05f515ef1f2badcb6ba0bde69daa3fa2677434
ms.sourcegitcommit: 35f167725bec5fd4fe131781a53d96b060cf232d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2022
ms.locfileid: "65873514"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-unenrolled-ios-devices"></a>登録されていないiOS デバイスにMicrosoft Defender for Endpointを展開する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> iOS上の Defender for Endpoint では、Web 保護機能を提供するために VPN が使用されます。 これは通常の VPN ではなく、デバイスの外部でトラフィックを受け取らないローカル/セルフループ VPN です。

## <a name="configure-microsoft-defender-for-endpoint-risk-signals-in-app-protection-policy-mam"></a>アプリ保護ポリシー (MAM) でMicrosoft Defender for Endpointリスクシグナルを構成する

モバイル デバイス管理 (MDM) シナリオでエンタープライズ ユーザーを既に保護しているiOSのMicrosoft Defender for Endpointでは、モバイル デバイス管理 (MDM) を使用して登録されていないデバイスのサポートがモバイル アプリ管理 (MAM) Intune に拡張されるようになりました。 また、モバイル アプリケーション管理 (MAM) にIntuneを引き続き使用しながら、他のエンタープライズ モビリティ管理ソリューションを使用するお客様にもこのサポートを拡張します。この機能を使用すると、アプリケーション内で組織のデータを管理および保護できます。

iOS脅威情報に関するMicrosoft Defender for Endpointは、これらのアプリを保護するために、Intune App Protection ポリシーによって利用されます。 アプリ保護ポリシー (APP) は、組織のデータが安全な状態にあるか、またはマネージド アプリ内に格納されることを保証するルールです。 マネージド アプリケーションにはアプリ保護ポリシーが適用されており、Intuneによって管理できます。  

iOSのMicrosoft Defender for Endpointでは、MAM の両方の構成がサポートされます
- **INTUNE MDM + MAM**: IT 管理者は、Intuneモバイル デバイス管理 (MDM) に登録されているデバイス上のアプリ保護ポリシーを使用してのみアプリを管理できます。
- **デバイス登録のない MAM**: デバイス登録のない MAM、または MAM-WE を使用すると、IT 管理者は、INTUNE MDM に登録されていないデバイスで [App Protection ポリシー](/mem/intune/apps/app-protection-policy)を使用してアプリを管理できます。 つまり、サードパーティ EMM プロバイダーに登録されているデバイスで Intune によりアプリを管理できます。 上記の両方の構成で使用するアプリを管理するには、Microsoft エンドポイント マネージャー[管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)でIntuneを使用する必要があります

この機能を有効にするには、管理者がMicrosoft Defender for EndpointとIntuneの間の接続を構成し、アプリ保護ポリシーを作成し、ターゲットデバイスとアプリケーションにポリシーを適用する必要があります。 
 
エンド ユーザーは、デバイスにMicrosoft Defender for Endpointをインストールし、オンボード フローをアクティブ化する手順も必要です。

### <a name="pre-requisites"></a>前提条件

1. **コネクタが有効になっていることを確認します**。 <br> [統合セキュリティ コンソール](https://security.microsoft.com)で **、設定** > **Endpoints** > **Advanced Features** に移動し、**Microsoft Intune接続** が有効になっていることを確認します。

  :::image type="content" source="images/enable-intune-connection.png" alt-text="Defender for Endpoint - Intune コネクタ" lightbox="images/enable-intune-connection.png":::

  
2. **Intune ポータルでコネクタが有効になっていることを確認します**。 <br> [Microsoft Endpoint Manager 管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)で、**Endpoint Security** >  に移動 **しMicrosoft Defender for Endpoint** 接続の状態が有効になっていることを確認します。

  :::image type="content" source="images/app-settings.png" alt-text="アプリケーションの設定" lightbox="images/app-settings.png":::

### <a name="create-an-app-protection-policy"></a>アプリ保護ポリシーを作成する
 
アプリ保護ポリシーを作成することで、Microsoft Defender for Endpointリスクシグナルに基づいてマネージド アプリのデータへのアクセスをブロックまたはワイプします。
Microsoft Defender for Endpointは、アプリ保護ポリシー (MAM とも呼ばれる) で使用される脅威信号を送信するように構成できます。 この機能を使用すると、Microsoft Defender for Endpointを使用してマネージド アプリを保護できます。

1. ポリシーを作成する <br>
アプリ保護ポリシー (APP) は、組織のデータが安全な状態にあるか、またはマネージド アプリ内に格納されることを保証するルールです。 ポリシーの例としては、ユーザーが "企業" データへのアクセスまたは移動を試みた場合や、アプリ内で禁止または監視されている一連の操作を試みた場合に適用されるルールがあります。 

:::image type="content" source="images/create-policy.png" alt-text="[アプリ保護 ポリシー] メニュー項目の [ポリシーの作成] タブ" lightbox="images/create-policy.png":::

2. アプリを追加する <br>
    a.  このポリシーをさまざまなデバイス上のアプリに適用する方法を選択します。 次に、少なくとも 1 つのアプリを追加します。 <br>
    このポリシーをアンマネージド デバイスに適用するかどうかを指定するには、このオプションを使用します。 また、任意の管理状態のデバイス上のアプリにポリシーをターゲットにすることもできます。
モバイル アプリ管理にはデバイス管理が必要ないため、マネージド デバイスとアンマネージド デバイスの両方で会社データを保護することができます。 管理の中心がユーザー ID になり、デバイスを管理する必要がなくなります。 企業は、MDM の有無にかかわらず、アプリ保護ポリシーを同時に使用できます。 たとえば、会社で支給されたスマートフォンと自分のタブレットの両方を使用する社員がいるとします。 会社のスマートフォンは MDM に登録されたうえでアプリ保護ポリシーによって保護されますが、個人のデバイスはアプリ保護ポリシーのみで保護されます。

    b. アプリの選択<br>
    管理対象アプリは、アプリ保護ポリシーが適用されたアプリであり、Intune で管理できます。 [Intune SDK](/mem/intune/developer/app-sdk) と統合されているか、Intune App Wrapping Toolによってラップされたすべてのアプリは、[Intune](/mem/intune/developer/apps-prepare-mobile-application-management)アプリ保護ポリシーを使用して管理できます。 これらのツールを使用して構築されている一般使用が可能な [Microsoft Intune による保護アプリ](/mem/intune/apps/apps-supported-intune-apps)の公式一覧を参照してください。

    *例: マネージド アプリとしてOutlookする*

     :::image type="content" source="images/managed-app.png" alt-text="左側のナビゲーション ウィンドウの [Microsoft Outlook] メニュー項目" lightbox="images/managed-app.png":::
  

 3. 保護ポリシーのサインイン セキュリティ要件を設定します。 <br>
[デバイス **の条件**] **> [許可されている最大デバイスの脅威レベルの設定**] を選択し、値を入力します。 次に、[**アクション] を選択します。** iOSのMicrosoft Defender for Endpointは、このデバイスの脅威レベルを共有します。

    
   :::image type="content" source="images/conditional-launch.png" alt-text="[デバイスの条件] ウィンドウ" lightbox="images/conditional-launch.png":::

4. ポリシーを適用する必要があるユーザー グループを割り当てます。<br>
  [ **含まれるグループ]** を選択します。 次に、関連するグループを追加します。 


MAM またはアプリ保護ポリシーの詳細については、[アプリ保護ポリシーの設定iOS](/mem/intune/apps/app-protection-policy-settings-ios)参照してください。

## <a name="deploy-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a>MAM または登録されていないデバイスにMicrosoft Defender for Endpointを展開する

iOSのMicrosoft Defender for Endpointは、アプリ保護ポリシーのシナリオを有効にし、Apple アプリ ストアで使用できます。

アプリの保護ポリシーが、Microsoft Defender for Endpointからのデバイス リスクシグナルを含むアプリ用に構成されている場合、ユーザーは、そのようなアプリを使用するときにMicrosoft Defender for Endpointをインストールするようにリダイレクトされます。 または、ユーザーは Apple アプリ ストアからアプリの最新バージョンを直接インストールすることもできます。
