---
title: Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する
description: 証明書の要件と Wi-Fi 接続
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
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
ms.openlocfilehash: 69cea241c81130fdee2ae734c372981e0349ab64
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035596"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する  
 
証明書ベースの認証は、Microsoft Managed Desktop を使用しているお客様に共通の要件です。 VPN ソリューションへの接続、または組織内Wi-Fiにアクセスするために、証明書が必要になる場合があります。   
 
Microsoft Managed Desktop デバイスは Azure Active Directory (Azure AD) に参加し、Microsoft Intune によって管理されるので、Intune と統合された簡易証明書登録プロトコル (SCEP) または公開キー暗号化標準 (PKCS) 証明書インフラストラクチャを使用して、このような証明書を展開する必要があります。    
 
## <a name="certificate-requirements"></a>証明書の要件 
 
ルート証明書は、SCEP または PKCS インフラストラクチャを介して証明書を展開するために必要です。 組織内の他のアプリケーションとサービスでは、ルート証明書を Microsoft Managed Desktop デバイスに展開する必要があります。    
 
SCEP または PKCS 証明書を Microsoft Managed Desktop に展開する前に、組織内のユーザーまたはデバイス証明書を必要とする各サービスの要件を収集する必要があります。 このアクティビティを簡単にするために、次のいずれかの計画テンプレートを使用できます。  
 
- [PKCS 証明書テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP 証明書テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fiの要件

エンタープライズ ネットワークに必要な構成をデバイスに自動的にWi-Fiするには、構成プロファイルをWi-Fiがあります。 Microsoft Managed Desktop を構成して、これらのプロファイルをデバイスに展開できます。 ネットワーク セキュリティでデバイスがローカル ドメインの一部である必要がある場合は、microsoft Managed Desktop デバイスとの互換性を確認するために、Wi-Fi ネットワーク インフラストラクチャを評価する必要があります (Microsoft Managed Desktop デバイスは Azure AD 参加のみ)。 
 
Microsoft Managed Desktop デバイスにWi-Fi構成を展開する前に、ネットワークごとに組織の要件をWi-Fiされます。 このアクティビティを簡単にするために、この WiFi プロファイル テンプレート [を使用できます](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)。
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>有線接続要件と 802.1x 認証 
 
802.1x 認証を使用してデバイスからローカル エリア ネットワーク (LAN) へのアクセスをセキュリティで保護する場合は、必要な構成の詳細を Microsoft Managed Desktop デバイスにプッシュする必要があります。 Microsoft Managed Desktop デバイスWindows 10 Version 1809以降は、WiredNetwork 構成サービス プロバイダー (CSP) を介した 802.1x 構成の展開をサポートします。 詳細については [、「WiredNetwork CSP のドキュメント」を参照](/windows/client-management/mdm/wirednetwork-csp) してください。 
 
Microsoft Managed Desktop デバイスに有線ネットワーク構成プロファイルを展開する前に、組織の有線企業ネットワークの要件を収集してください。 そのために、以下の手順に従ってください。 
 
 
1. 既存の 802.1x プロファイルが構成され、LAN ネットワークに接続されているデバイスにサインオンします。  
2. 管理者資格情報を使用してコマンド プロンプトを開きます。 
3. netsh インターフェイス ショー インターフェイスを実行して **LAN インターフェイス名を検索します**。 
4. netsh lan エクスポート プロファイル フォルダー= を実行して **LAN プロファイル XML をエクスポートします。 Interface="interface_name" .** 
5. Microsoft Managed Desktop デバイスでエクスポートしたプロファイルをテストする必要がある場合は、netsh lan add profile **filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME" を実行します**。 
 
 
## <a name="deploy-certificate-infrastructure"></a>証明書インフラストラクチャの展開  
 
Intune に既存の SCEP または PKCS インフラストラクチャが既に存在し、この方法が要件を満たしている場合は、Microsoft Managed Desktop でも使用できます。 SCEP または PKCS インフラストラクチャが既に存在しない場合は、準備する必要があります。  
 
詳細については、「[Microsoft Intune でデバイスの証明書プロファイルを構成する](/intune/certificates-configure)」を参照してください。 
 
 
 
## <a name="deploy-a-lan-profile"></a>LAN プロファイルの展開 
 
LAN プロファイルをエクスポートしたら、次の手順に従って Microsoft Managed Desktop のポリシーを準備できます。   
 
1. 次の設定を使用Microsoft Intune LAN プロファイルのカスタム プロファイルを作成します (「Intune でデバイスのカスタム設定Windows 10使用する」[を参照してください](/intune/custom-settings-windows-10))。 [**カスタム OMA-URI 設定] で、[追加****]** を選択し、次の値を入力します。 
    - 名前: *モダン Workplace-Windows 10 LAN プロファイル* 
    - 説明: 設定の概要および他の重要な詳細がわかる説明を入力します。 
    - OMA-URI (大文字と小文字の区別): *Enter ./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - データ型: [文字列] **(XML ファイル) を選択します**。 
    - カスタム XML: アップロード XML ファイルを作成します。
2. カスタム プロファイルをモダン ワークプレース デバイス *- テスト グループに割り当* てる。
3. テスト展開グループにあるデバイスを使用して、必要と感じるテストを行います。 成功した場合は、カスタム プロファイルをモダン ワークプレース デバイス *( First*、 Modern *Workplace Devices – Fast*、 および Modern Workplace Devices – Broad グループ) に割り *当* てる必要があります。
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>証明書と Wi-Fi/VPN プロファイルの展開 
 
 
証明書とプロファイルを展開するには、次の手順を実行します。

1. ルート証明書と中間証明書のそれぞれについてプロファイルを作成します (「信頼できる証明書プロファイルの作成 [」を参照してください](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles)。 これらの各プロファイルには、DD/MM/YYYYY 形式の有効期限を含む説明が必要です。 **証明書プロファイルには有効期限が必要です。**
2. SCEP または PKCS 証明書ごとにプロファイルを作成します [(「SCEP](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) 証明書プロファイルを作成する」または [「PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)証明書プロファイルを作成する」を参照) これらの各プロファイルには、DD/MM/YYYY 形式の有効期限を含む説明が必要です。 **証明書プロファイルには有効期限が必要です。**
3. 企業の WiFi ネットワークごとにプロファイルを作成します (「Wi-Fi の設定」を参照[)、Windows 10を参照してください](/intune/wi-fi-settings-windows)。
4. 企業 VPN ごとにプロファイルを作成します (Intune を使用して VPN 接続をWindows 10、Windows [Holographic](/intune/vpn-settings-windows-10)デバイスの設定を参照してください)。
5. プロファイルをモダン ワークプレース デバイス *- テスト グループに割り当* てる。
6. テスト展開グループにあるデバイスを使用して、必要と感じるテストを行います。 成功した場合は、カスタム プロファイルをモダン ワークプレース デバイス *( First*、 Modern *Workplace Devices – Fast*、 および Modern Workplace Devices – Broad グループ) に割り *当* てる必要があります。

 
## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop の準備をする手順

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
2. [準備状況の評価ツール](readiness-assessment-tool.md)を実行します。
1. [ポータル サイト](../get-started/company-portal.md)を購入します。
1. [ゲスト アカウントの前提条件](guest-accounts.md)を確認します。
1. [ネットワーク構成](network.md)をチェックします。
1. 証明書とネットワーク プロファイルを準備します (この記事)。
1. [データへのユーザー アクセスを準備します](authentication.md)。
1. [アプリを準備します](apps.md)。
1. [マップ済みドライブを準備します](mapped-drives.md)。
1. [印刷リソースを準備します](printing.md)。
1. [デバイス名](address-device-names.md)をアドレス指定します。
