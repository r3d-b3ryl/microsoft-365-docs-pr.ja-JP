---
title: アプリ保護ポリシー (MAM) を使用してMicrosoft Defender for Endpointリスクシグナルを構成する
description: App Protection ポリシーを使用してMicrosoft Defender for Endpointリスクシグナルを構成する方法について説明します
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, 構成, MAM, App Protectection Policies, Managed app
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: shthota
author: shthota
manager: dansimp
ms.localizationpriority: medium
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d6d9561f381771fb322a281f33f840c27ce61f90
ms.sourcegitcommit: f1b3ecde15e5cbbeadaf51b2cadb6b1d677fc265
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2022
ms.locfileid: "67437800"
---
# <a name="configure-microsoft-defender-for-endpoint-risk-signals-using-app-protection-policies-mam"></a>アプリ保護ポリシー (MAM) を使用してMicrosoft Defender for Endpointリスクシグナルを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



モバイル デバイス管理 (MDM) シナリオでエンタープライズ ユーザーを既に保護している Android のMicrosoft Defender for Endpointは、モバイル デバイス管理 (MDM) を使用して登録されていないデバイスのサポートをモバイル アプリ管理 (MAM) Intune に拡張するようになりました。 また、モバイル アプリケーション管理 (MAM) にIntuneを引き続き使用しながら、他のエンタープライズ モビリティ管理ソリューションを使用するお客様にもこのサポートを拡張します。この機能を使用すると、アプリケーション内で組織のデータを管理および保護できます。

Android の脅威情報に関するMicrosoft Defender for Endpointは、これらのアプリを保護するために、Intune App Protection ポリシーによって適用されます。 アプリ保護ポリシー (APP) は、組織のデータが安全な状態にあるか、またはマネージド アプリ内に格納されることを保証するルールです。 マネージド アプリケーションにはアプリ保護ポリシーが適用されており、Intuneによって管理できます。  

Android 上のMicrosoft Defender for Endpointでは、MAM の両方の構成がサポートされます
- **INTUNE MDM + MAM**: IT 管理者は、Intuneモバイル デバイス管理 (MDM) に登録されているデバイス上のアプリ保護ポリシーを使用してのみアプリを管理できます。
- **デバイス登録のない MAM**: デバイス登録のない MAM、または MAM-WE を使用すると、IT 管理者は、INTUNE MDM に登録されていないデバイスで [App Protection ポリシー](/mem/intune/apps/app-protection-policy)を使用してアプリを管理できます。 このプロビジョニングは、サードパーティの EMM プロバイダーに登録されているデバイス上のIntuneによってアプリを管理できることを意味します。 これらの両方の構成でアプリを管理するには、[Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)でIntuneを使用する必要があります。

この機能を有効にするには、管理者がMicrosoft Defender for EndpointとIntuneの間の接続を構成し、アプリ保護ポリシーを作成し、ターゲットデバイスとアプリケーションにポリシーを適用する必要があります。 
 
エンド ユーザーは、デバイスにMicrosoft Defender for Endpointをインストールし、オンボード フローをアクティブ化する手順も必要です。


## <a name="admin-prerequisites"></a>管理前提条件

- **Microsoft Defender for Endpoint-Intune コネクタが有効になっていることを検証する**

  a. security.microsoft.com に移動します。 

  b. [**接続>詳細設定]> [エンドポイント**> Microsoft Intune設定] を選択します。

  c. 接続がオンになっていない場合は、トグルを選択してオンにし、[ **設定の保存]** を選択します。

  :::image type="content" source="images/enable-intune-connection.png" alt-text="Microsoft 365 Defender ポータルの [高度な機能] セクション" lightbox="images/enable-intune-connection.png":::

  d. **Microsoft エンドポイント マネージャー (Intune)** に移動し、Microsoft Defender for Endpoint-Intune コネクタが有効かどうかを検証します。

  :::image type="content" source="images/validate-intune-connector.png" alt-text="Microsoft 365 Defender ポータルの intune コネクタの状態ウィンドウ" lightbox="images/validate-intune-connector.png":::

- **Android Connector for App Protection Policy (APP) でMicrosoft Defender for Endpointを有効にする**
  
  アプリ保護 ポリシー用に microsoft エンドポイント マネージャーでコネクタIntune構成します。

  a. **[テナント管理] > [コネクタとトークン] > Microsoft Defender for Endpoint** に移動します。

  b. Android のアプリ保護ポリシーのトグルをオンにします (次のスクリーンショットに示すように)。

  c. **[保存]** を選択します。

  :::image type="content" source="images/app-settings.png" alt-text="Microsoft 365 Defender ポータルの [アプリケーション設定] ウィンドウ" lightbox="images/app-settings.png":::

- **アプリ保護ポリシーを作成する** 
 
アプリ保護ポリシーを作成することで、Microsoft Defender for Endpointリスクシグナルに基づいてマネージド アプリのデータへのアクセスをブロックまたはワイプします。
Microsoft Defender for Endpointは、アプリ保護ポリシー (MAM とも呼ばれる) で使用される脅威信号を送信するように構成できます。 この機能を使用すると、Microsoft Defender for Endpointを使用してマネージド アプリを保護できます。

1. ポリシーを作成する <br>
アプリ保護ポリシー (APP) は、組織のデータが安全な状態にあるか、またはマネージド アプリ内に格納されることを保証するルールです。 ポリシーの例としては、ユーザーが "企業" データへのアクセスまたは移動を試みた場合や、アプリ内で禁止または監視されている一連の操作を試みた場合に適用されるルールがあります。 

:::image type="content" source="images/create-policy.png" alt-text="Microsoft 365 Defender ポータルの [アプリ保護 ポリシー] ページの [ポリシーの作成] タブ" lightbox="images/create-policy.png":::

2. アプリを追加する <br>
    a. このポリシーをさまざまなデバイス上のアプリに適用する方法を選択します。 次に、少なくとも 1 つのアプリを追加します。 <br>
    このポリシーをアンマネージド デバイスに適用するかどうかを指定するには、このオプションを使用します。 Android では、ポリシーを Android Enterprise、デバイス 管理、またはアンマネージド デバイスに適用するように指定できます。 また、任意の管理状態のデバイス上のアプリにポリシーをターゲットにすることもできます。
モバイル アプリ管理にはデバイス管理が必要ないため、マネージド デバイスとアンマネージド デバイスの両方で会社データを保護することができます。 管理の中心がユーザー ID になり、デバイスを管理する必要がなくなります。 企業は、MDM の有無にかかわらず、アプリ保護ポリシーを同時に使用できます。 たとえば、会社で支給されたスマートフォンと自分のタブレットの両方を使用する社員がいるとします。 会社のスマートフォンは MDM に登録されたうえでアプリ保護ポリシーによって保護されますが、個人のデバイスはアプリ保護ポリシーのみで保護されます。

    b. アプリの選択<br>
    管理対象アプリは、アプリ保護ポリシーが適用されたアプリであり、Intune で管理できます。 [Intune SDK](/mem/intune/developer/app-sdk) と統合されているか、Intune App Wrapping Toolによってラップされたすべてのアプリは、[Intune](/mem/intune/developer/apps-prepare-mobile-application-management)アプリ保護ポリシーを使用して管理できます。 これらのツールを使用して構築されている一般使用が可能な [Microsoft Intune による保護アプリ](/mem/intune/apps/apps-supported-intune-apps)の公式一覧を参照してください。

    *例: マネージド アプリとしての Outlook*

  :::image type="content" source="images/managed-app.png" alt-text="Microsoft 365 Defender ポータルの [パブリック アプリ] ウィンドウ" lightbox="images/managed-app.png":::


 3. 保護ポリシーのサインイン セキュリティ要件を設定します。 <br>
[デバイス **の条件**] **> [許可されている最大デバイスの脅威レベルの設定**] を選択し、値を入力します。 次に、[**アクション] を選択します。** Android 上のMicrosoft Defender for Endpointは、この Device Threat Level を共有します。

  :::image type="content" source="images/conditional-launch.png" alt-text="Microsoft 365 Defender ポータルの [デバイスの条件] ウィンドウ" lightbox="images/conditional-launch.png":::
  
- **ポリシーを適用する必要があるユーザー グループを割り当てます。**<br>
  [ **含まれるグループ]** を選択します。 次に、関連するグループを追加します。 

    :::image type="content" source="images/assignment.png" alt-text="Microsoft 365 Defender ポータルの [含まれるグループ] ウィンドウ" lightbox="images/assignment.png":::


## <a name="end-user-prerequisites"></a>エンド ユーザーの前提条件
- ブローカー アプリをインストールする必要があります
    - Intune ポータル サイト
    
- ユーザーがマネージド アプリに必要なライセンスを持ち、アプリをインストールしている

### <a name="end-user-onboarding"></a>エンド ユーザーオンボーディング 

1. Outlook など、マネージド アプリケーションにサインインします。 デバイスが登録され、アプリケーション保護ポリシーがデバイスに同期されます。 アプリケーション保護ポリシーは、デバイスの正常性状態を認識します。  

2. **[続行]** を選択します。 Android アプリでMicrosoft Defender for Endpointのダウンロードと設定を推奨する画面が表示されます。

3. [**ダウンロード**] を選択します。 アプリ ストア (Google play) にリダイレクトされます。 

4.  Microsoft Defender for Endpoint (モバイル) アプリをインストールし、マネージド アプリのオンボード画面を起動します。

  :::image type="content" source="images/download-mde.png" alt-text="MDE をダウンロードし、アプリのオンボード画面を起動する手順を含む図のページ" lightbox="images/download-mde.png":::
  

5.  [ **続行] > [起動]** をクリックします。 Microsoft Defender for Endpoint アプリのオンボード/アクティブ化フローが開始されます。 手順に従ってオンボードを完了します。 管理対象アプリのオンボード画面に自動的にリダイレクトされます。これで、デバイスが正常であることを示します。

6. [ **続行]** を選択して、マネージド アプリケーションにログインします。 

## <a name="configure-privacy-controls"></a>プライバシー制御を構成する 
>[!IMPORTANT]
>MAM のMicrosoft Defender for Endpointのプライバシー制御はパブリック プレビュー段階にあります。 次の情報は、市販される前に大幅に変更される可能性のあるプレリリース済み製品に関連しています。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。
>**この機能を試したり、フィードバックを提供したりする場合は、mdatpmobile@microsoft.com にお問い合わせください。**

管理者は、次の手順を使用してプライバシーを有効にし、対応する脅威に対するアラート レポートの一部としてドメイン名、アプリの詳細、ネットワーク情報を収集することはできません。

1. Microsoft エンドポイント マネージャー管理センターで、[**アプリ> アプリ構成ポリシー] > [>管理アプリの追加] に移動します**。

2. ポリシーに **名前** を付けます。

3. [パブリック アプリの選択] で、ターゲット アプリとして **[Microsoft Defender for Endpoint**] を選択します。

4. [設定] ページの [全般構成設定] で、キーと値として **DefenderExcludeURLInReport**、 **DefenderExcludeAppInReport** を true として追加します。

5. このポリシーをユーザーに割り当てます。 既定では、この値は false に設定されます。

6. ポリシーを確認して作成します。

## <a name="optional-permissions"></a>オプションのアクセス許可 
>[!IMPORTANT]
>Microsoft Defender for Endpointに対するオプションのアクセス許可はパブリック プレビュー段階にあります。 次の情報は、市販される前に大幅に変更される可能性のあるプレリリース済み製品に関連しています。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。
>**この機能を試したり、フィードバックを提供したりする場合は、mdatpmobile@microsoft.com にお問い合わせください。**

Android のMicrosoft Defender for Endpointでは、オンボード フローでオプションのアクセス許可が有効になります。 現在、MDE で必要なアクセス許可は、オンボード フローで必須です。 この機能を使用すると、管理者は、オンボード中に必須の VPN とアクセシビリティのアクセス許可を強制することなく、MAM ポリシーを使用して Android デバイスに MDE を展開できます。 エンド ユーザーは、必須のアクセス許可なしでアプリをオンボードでき、後でこれらのアクセス許可を確認できます。 

### <a name="configure-optional-permission"></a>オプションのアクセス許可を構成する

次の手順を使用して、デバイスに対するオプションのアクセス許可を有効にします。

1. Microsoft エンドポイント マネージャー管理センターで、[**アプリ> アプリ構成ポリシー] > [>管理アプリの追加] に移動します**。

2. ポリシーに **名前** を付けます。

3. パブリック アプリ **で [Microsoft Defender for Endpoint*** ] を選択します。

4. [設定] ページで、[ **構成デザイナーの使用** ] を選択し、 **DefenderOptionalVPN** または **DefenderOptionalAccessibility** を追加するか、キーと値の **両方** の型をブール値として追加します。 

5. オプションのアクセス許可を有効にするには、 **true** として値を入力し、このポリシーをユーザーに割り当てます。 既定では、この値は false に設定されます。
キーが true に設定されているユーザーの場合、ユーザーはこれらのアクセス許可を与えずにアプリをオンボードできます。

6. **[次へ**] を選択し、対象となるデバイス/ユーザーにこのプロファイルを割り当てます。

### <a name="user-flow"></a>ユーザー フロー 

ユーザーは、アプリをインストールして開き、オンボード プロセスを開始できます。

1. 管理者がオプションのアクセス許可を設定している場合、ユーザーは VPN またはアクセシビリティのアクセス許可をスキップするか、またはその両方をスキップしてオンボードを完了するかを選択できます。
2. ユーザーがこれらのアクセス許可をスキップした場合でも、デバイスはオンボードでき、ハートビートが送信されます。
3. アクセス許可が無効になっているため、Web 保護はアクティブになりません。 いずれかのアクセス許可が与えられた場合、部分的にアクティブになります。
4. 後で、ユーザーはアプリ内から Web 保護を有効にすることができます。 これにより、デバイスに VPN 構成がインストールされます。

>[!NOTE] 
> オプションのアクセス許可設定は、[Web 保護の無効化] 設定とは異なります。 オプションのアクセス許可は、オンボード中にアクセス許可をスキップする場合にのみ役立ちますが、エンド ユーザーは後で確認して有効にできますが、Web 保護を無効にすると、ユーザーは Web Protection なしでMicrosoft Defender for Endpoint アプリをオンボードできます。 後で有効にすることはできません。

## <a name="related-topics"></a>関連項目

- [Android 用 Microsoft Defender for Endpoint の概要](microsoft-defender-endpoint-android.md)
- [Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開](android-intune.md)
