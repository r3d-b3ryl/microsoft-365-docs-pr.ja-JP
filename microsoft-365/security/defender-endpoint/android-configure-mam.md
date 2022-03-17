---
title: アプリ保護ポリシー (MAM) を使用して Microsoft Defender for Endpoint リスクシグナルを構成する
description: アプリ保護ポリシーを使用して Microsoft Defender for Endpoint リスクシグナルを構成する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mde, android, configuration, MAM, App Protectection Policies, Managed app
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
ms.openlocfilehash: 5c18d5e9fbf628f5d4e4373b866fa300c193ac30
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525530"
---
# <a name="configure-microsoft-defender-for-endpoint-risk-signals-using-app-protection-policies-mam"></a>アプリ保護ポリシー (MAM) を使用して Microsoft Defender for Endpoint リスクシグナルを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



モバイル デバイス管理 (MDM) シナリオでエンタープライズ ユーザーを既に保護している Android 上の Microsoft Defender for Endpoint は、Intune モバイル デバイス管理 (MDM) を使用して登録されていないデバイスのモバイル アプリ管理 (MAM) のサポートを拡張しました。 また、このサポートは、他のエンタープライズ モビリティ管理ソリューションを使用しているお客様にも拡張しますが、モバイル アプリケーション管理 (MAM) には Intune を使用します。この機能を使用すると、アプリケーション内で組織のデータを管理および保護できます。

Microsoft Defender for Endpoint on Android の脅威情報は、Intune アプリ保護ポリシーによってこれらのアプリを保護するために活用されます。 アプリ保護ポリシー (APP) は、組織のデータが安全な状態にあるか、またはマネージド アプリ内に格納されることを保証するルールです。 管理アプリケーションにはアプリ保護ポリシーが適用され、Intune で管理できます。  

Android 上のエンドポイント用 Microsoft Defender は、MAM の両方の構成をサポートしています
- **Intune MDM + MAM**: IT 管理者は、Intune モバイル デバイス管理 (MDM) に登録されているデバイスでアプリ保護ポリシーを使用してアプリのみを管理できます。
- **デバイス登録のない** MAM: デバイス登録なしの MAM、または MAM-WE を使用すると、IT 管理者は Intune MDM [](/mem/intune/app/app-protection-policy) に登録されていないデバイスでアプリ保護ポリシーを使用してアプリを管理できます。 つまり、サードパーティ EMM プロバイダーに登録されているデバイスで Intune によりアプリを管理できます。 上記の構成の両方で使用するアプリを管理するには、管理者センターで Intune を[Microsoft エンドポイント マネージャーする必要があります。](https://go.microsoft.com/fwlink/?linkid=2109431)

この機能を有効にするには、管理者が Microsoft Defender for Endpoint と Intune 間の接続を構成し、アプリ保護ポリシーを作成し、対象のデバイスとアプリケーションにポリシーを適用する必要があります。 
 
エンド ユーザーは、デバイスに Microsoft Defender for Endpoint をインストールし、オンボーディング フローをアクティブ化するための手順を実行する必要があります。


## <a name="admin-prerequisites"></a>管理者の前提条件

- **Microsoft Defender for Endpoint-Intuneが有効になっているか確認する**

  a.  [次へ] security.microsoft.com。 

  b. [**接続設定 >有効>高度な機能> Microsoft Intuneエンドポイント]** を選択します。

  c. 接続が有効ではない場合は、トグルを選択してオンにし、[基本設定の保存 **] を選択します**。

  ![Defender for Endpoint -Intune コネクタのイメージ](images/enable-intune-connection.png)

  d. [Microsoft Defender **for Microsoft エンドポイント マネージャー (Intune)** に移動し、Microsoft Defender for Endpoint-Intune有効かどうかを検証します。

  ![Intune のコネクタEndpoint-Intune Defender のイメージ](images/validate-intune-connector.png)

- **アプリ保護ポリシー (APP) の Android コネクタで Microsoft Defender for Endpoint を有効にする**
  
  アプリ保護ポリシー用に Intune Microsoft エンドポイント マネージャーコネクタを構成します。

  a.  [テナントの **管理] >およびトークン > Microsoft Defender for Endpoint に移動します**。

  b. Android のアプリ保護ポリシーのトグルをオンにします (次のスクリーンショットを参照)。

  c. **[保存]** を選択します。

  ![アプリの設定](images/app-settings.png)

- **アプリ保護ポリシーを作成する** 
 
アプリ保護ポリシーを作成して、Microsoft Defender for Endpoint リスクシグナルに基づいて管理アプリのデータへのアクセスをブロックまたはワイプします。
Microsoft Defender for Endpoint は、アプリ保護ポリシー (APP、 MAM とも呼ばれる) で使用される脅威信号を送信するように構成できます。 この機能を使用すると、Microsoft Defender for Endpoint を使用して管理対象アプリを保護できます。

1. ポリシーを作成する <br>
アプリ保護ポリシー (APP) は、組織のデータが安全な状態にあるか、またはマネージド アプリ内に格納されることを保証するルールです。 ポリシーの例としては、ユーザーが "企業" データへのアクセスまたは移動を試みた場合や、アプリ内で禁止または監視されている一連の操作を試みた場合に適用されるルールがあります。 

![ポリシー作成のイメージ](images/create-policy.png)

2. アプリを追加する <br>
    a.  このポリシーをさまざまなデバイス上のアプリに適用する方法を選択します。 次に、少なくとも 1 つのアプリを追加します。 <br>
    このポリシーが管理されていないデバイスに適用されるかどうかを指定するには、このオプションを使用します。 Android の場合は、Android デバイス、デバイス管理者、または管理Enterpriseポリシーを指定できます。 また、任意の管理状態のデバイス上のアプリにポリシーをターゲットにすることもできます。
モバイル アプリ管理にはデバイス管理が必要ないため、マネージド デバイスとアンマネージド デバイスの両方で会社データを保護することができます。 管理の中心がユーザー ID になり、デバイスを管理する必要がなくなります。 企業は、MDM を使用する場合と使用しない場合でも、アプリ保護ポリシーを同時に使用できます。 たとえば、会社で支給されたスマートフォンと自分のタブレットの両方を使用する社員がいるとします。 会社の電話は MDM に登録され、アプリ保護ポリシーによって保護され、個人用デバイスはアプリ保護ポリシーでのみ保護されます。

    b. [アプリの選択]<br>
    管理対象アプリは、アプリ保護ポリシーが適用されたアプリであり、Intune で管理できます。 [Intune SDK](/mem/intune/developer/app-sdk) に統合されたアプリ、または Intune アプリによってラップされたアプリは、Intune アプリ[App Wrapping Tool](/mem/intune/developer/apps-prepare-mobile-application-management)ポリシーを使用して管理できます。 これらのツールを使用して構築されている一般使用が可能な [Microsoft Intune による保護アプリ](/mem/intune/apps/apps-supported-intune-apps)の公式一覧を参照してください。

    *例: Outlookアプリとして使用する*

    ![管理Outlookとしてのイメージ の設定](images/managed-app.png)

 3. 保護ポリシーのサインイン セキュリティ要件を設定します。 <br>
[ **デバイスの条件>最大許容** デバイス脅威レベルの設定] を選択 **し、値** を入力します。 次に、[  **アクション: アクセスをブロックする] を選択します**。 Android 上のエンドポイント用 Microsoft Defender は、このデバイス脅威レベルを共有します。

    ![条件付き起動のイメージ](images/conditional-launch.png)


- **ポリシーを適用する必要があるユーザー グループを割り当てる。**<br>
  [含 **まれるグループ] を選択します**。 次に、関連するグループを追加します。 

    ![assigments のイメージ](images/assignment.png)


## <a name="end-user-prerequisites"></a>エンド ユーザーの前提条件
- ブローカー アプリをインストールする必要がある
    - Intune ポータル サイト
    
- ユーザーが管理アプリに必要なライセンスを持ち、アプリがインストールされている

### <a name="end-user-onboarding"></a>エンド ユーザーのオンボーディング 

1. 管理アプリケーションにサインインします (たとえば、Outlook。 デバイスが登録され、アプリケーション保護ポリシーがデバイスに同期されます。 アプリケーション保護ポリシーは、デバイスの正常性状態を認識します。  

2. **[続行]** を選択します。 Android アプリで Microsoft Defender for Endpoint のダウンロードとセットアップを推奨する画面が表示されます。

3. [**ダウンロード**] を選択します。 アプリ ストア (Google プレイ) にリダイレクトされます。 

4.  Microsoft Defender for Endpoint (Mobile) アプリをインストールし、管理アプリのオンボーディング画面を起動します。

  ![MDE をインストールし、管理アプリのオンボーディング画面を起動する](images/download-mde.png)

5.  [続行 **] をクリック>起動します**。 Microsoft Defender for Endpoint アプリのオンボーディング/アクティブ化フローが開始されます。 手順に従ってオンボーディングを完了します。 [管理アプリのオンボーディング] 画面に自動的にリダイレクトされ、デバイスが正常に機能する状態が示されます。

6. [ **続行] を** 選択して管理アプリケーションにログインします。 



## <a name="related-topics"></a>関連項目

- [Android 用 Microsoft Defender for Endpoint の概要](microsoft-defender-endpoint-android.md)
- [Microsoft Intune を使用した Android 用 Microsoft Defender for Endpoint の展開](android-intune.md)
