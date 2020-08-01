---
title: Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する
description: 証明書/wifi/lan
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: c7c57861986d275165484ae726140720a75da88e
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530033"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する  
 
Microsoft マネージドデスクトップを使用しているお客様にとって、証明書ベースの認証は一般的な要件です。 Wi-fi または LAN にアクセスしたり、VPN ソリューションに接続したり、組織内の内部リソースにアクセスしたりするには、証明書が必要になることがあります。   
 
Microsoft マネージドデスクトップデバイスは Azure Active Directory (Azure AD) に参加しており、Microsoft Intune で管理されているため、このような証明書は、Intune と統合された簡易証明書登録プロトコル (SCEP) または公開キー暗号化標準 (PKCS) 証明書インフラストラクチャを使用して展開する必要があります。    
 
## <a name="certificate-requirements"></a>証明書の要件 
 
ルート証明書は、SCEP または PKCS インフラストラクチャを使用して証明書を展開するために必要です。 組織内の他のアプリケーションやサービスでは、Microsoft マネージドデスクトップデバイスにルート証明書を展開する必要がある場合があります。    
 
SCEP または PKCS 証明書を Microsoft マネージドデスクトップに展開する前に、組織内のユーザーまたはデバイス証明書を必要とする各サービスの要件を収集する必要があります。 これを簡単にするために、次の計画テンプレートのいずれかを使用できます。  
 
- [PKCS 証明書テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP 証明書テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

>[!NOTE]
>現時点では、EAP の種類を使用している場合、Microsoft マネージドデスクトップへの Wi-fi プロファイルの展開では、SCEP 証明書プロファイルのみがサポートされています。 PKCS 証明書プロファイルはサポートされていません。 リファレンスについては、「 [Intune で Windows 10 デバイスの wi-fi 設定を追加](https://docs.microsoft.com/intune/wi-fi-settings-windows)する」を参照してください。

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-fi 接続の要件

エンタープライズネットワークの必要な Wi-fi 構成でデバイスを自動的に提供できるようにするには、Wi-fi 構成プロファイルが必要になることがあります。 これらのプロファイルをデバイスに展開するように Microsoft Managed Desktop を構成できます。 ネットワークセキュリティがローカルドメインの一部となるデバイスを必要とする場合は、Wi-fi ネットワークインフラストラクチャを評価して、Microsoft マネージドデスクトップデバイス (Microsoft マネージデスクトップデバイスが Azure AD に参加している場合のみ) と互換性があることを確認する必要がある場合もあります。 
 
Wi-fi 構成を Microsoft マネージドデスクトップデバイスに展開する前に、各 wi-fi ネットワークに対する組織の要件を収集する必要があります。 これを簡単にするために、この[WiFi プロファイルテンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)を使用することができます。
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>ワイヤード接続の要件と 802.1 x 認証 
 
802.1 x 認証を使用してデバイスからローカルエリアネットワーク (LAN) へのアクセスをセキュリティで保護する場合は、Microsoft マネージドデスクトップデバイスに必要な構成の詳細をプッシュする必要があります。 Windows 10 バージョン1809以降を実行している Microsoft マネージドデスクトップデバイスは、WiredNetwork configuration service provider (CSP) を介して 802.1 x 構成を展開するためにサポートされています。 詳細については、「 [Wirednetwork CSP](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp)のドキュメント」を参照してください。 
 
ワイヤードネットワーク構成プロファイルを Microsoft マネージドデスクトップデバイスに展開する前に、有線の企業ネットワークに対する組織の要件を収集します。 そのために、以下の手順に従ってください。 
 
 
1. 既存の 802.1 x プロファイルが構成されており、LAN ネットワークに接続されているデバイスにサインオンします。  
2. 管理者の資格情報を使用してコマンドプロンプトを開きます。 
3. **Netsh インターフェイス表示インターフェイス**を実行して、LAN インターフェイス名を検索します。 
4. Netsh lan エクスポートプロファイルフォルダー = を実行して、LAN プロファイル XML をエクスポートし**ます。 Interface = "interface_name"** です。 
5. エクスポートされたプロファイルを Microsoft マネージドデスクトップデバイスでテストする必要がある場合は、 **netsh lan add profile filename = "PATH_AND_FILENAME.xml" interface = "INTERFACE_NAME"** を実行します。 
 
 
## <a name="deploy-certificate-infrastructure"></a>証明書インフラストラクチャを展開する  
 
既存の SCEP または PKCS インフラストラクチャが既に Intune にインストールされていて、要件を満たしている場合は、Microsoft マネージドデスクトップでも使用できます。 SCEP または PKCS インフラストラクチャが既に存在しない場合は、いずれかを準備する必要があります。  
 
詳細については、「 [Microsoft Intune でデバイスの証明書プロファイルを構成する](https://docs.microsoft.com/intune/certificates-configure)」を参照してください。 
 
 
 
## <a name="deploy-a-lan-profile"></a>LAN プロファイルを展開する 
 
LAN プロファイルをエクスポートしたら、次の手順に従って Microsoft マネージドデスクトップのポリシーを準備することができます。   
 
1. 次の設定を使用して、Microsoft Intune で LAN プロファイル用のカスタムプロファイルを作成します (「 [Intune で Windows 10 デバイスのカスタム設定を使用する](https://docs.microsoft.com/intune/custom-settings-windows-10)」を参照してください)。 [**カスタム OMA-URI 設定**] で、[**追加**] を選択し、次の値を入力します。 
    - Name:*モダンワークプレース-Windows 10 LAN プロファイル* 
    - [説明]: 設定の概要とその他の重要な詳細情報を示す説明を入力します。 
    - OMA URI (大文字と小文字を区別): */Device/Vendor/MSFT/WiredNetwork/LanXML*
    - データ型: 選択**文字列 (XML ファイル)**。 
    - カスタム XML: エクスポートされた XML ファイルをアップロードします。
2. Microsoft managed desktop Admin portal を使用して Microsoft managed Desktop IT 操作に対するサポート要求を送信し、構成プロファイルを確認して "モダン Workplace Devices – Test" に展開します。 Microsoft マネージドデスクトップ IT 操作では、管理ポータルのサポート要求によって要求が完了したことが通知されます。
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>証明書と Wi-fi/VPN プロファイルを展開する 
 
 
証明書とプロファイルを展開するには、次の手順を実行します。

1. ルート証明書と中間証明書のそれぞれのプロファイルを作成します (「[信頼された証明書プロファイルを作成する](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles)」を参照してください。 これらの各プロファイルには、有効期限が DD/MM/YYYY 形式で記述されている必要があります。 **有効期限のない証明書プロファイルは展開されません。**
2. 各 SCEP または PKCS 証明書のプロファイルを作成する (「 [scep 証明書プロファイルを作成する](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile)」または「 [pkcs 証明書プロファイルを作成](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)する」を参照) これらの各プロファイルには、有効期限が DD/MM/YYYY 形式で記述されている必要があります。 **有効期限のない証明書プロファイルは展開されません。**
3. 各企業の WiFi ネットワークのプロファイルを作成します ( [Windows 10 以降のデバイスの wi-fi 設定を](https://docs.microsoft.com/intune/wi-fi-settings-windows)参照してください)。
4. 企業 VPN ごとにプロファイルを作成します ( [Intune を使用した VPN 接続を追加するには、「windows 10 および Windows Holographic デバイスの設定」を](https://docs.microsoft.com/intune/vpn-settings-windows-10)参照してください)。
5. 「証明書の展開」または「Wi-fi Profile Deployment」というタイトルのサポート要求を、microsoft Managed desktop 管理ポータルを使用して、構成プロファイルを確認して「モダン Workplace Devices – Test」に展開する microsoft Managed Desktop IT の操作に送信します。 Microsoft マネージドデスクトップ IT 操作では、管理ポータルのサポート要求によって要求が完了したことが通知されます。 
 
 
