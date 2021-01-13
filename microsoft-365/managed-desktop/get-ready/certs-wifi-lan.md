---
title: Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する
description: certs/wifi/lan
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
ms.openlocfilehash: cf31778d773a271ead6a1745197f04eca127ab5d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841097"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する  
 
証明書ベースの認証は、Microsoft マネージド デスクトップを使用しているお客様に共通の要件です。 VPN ソリューションに接続したり、組織内Wi-Fiにアクセスしたりするために、証明書が必要になる場合があります。   
 
Microsoft マネージド デスクトップ デバイスは Azure Active Directory (Azure AD) に参加し、Microsoft Intune によって管理されているので、Intune と統合された簡易証明書登録プロトコル (SCEP) または公開キー暗号化標準 (PKCS) 証明書インフラストラクチャを使用して、このような証明書を展開する必要があります。    
 
## <a name="certificate-requirements"></a>証明書の要件 
 
SCEP または PKCS インフラストラクチャを介して証明書を展開するには、ルート証明書が必要です。 組織内の他のアプリケーションやサービスでは、ルート証明書を Microsoft マネージド デスクトップ デバイスに展開する必要がある場合があります。    
 
SCEP または PKCS 証明書を Microsoft マネージド デスクトップに展開する前に、組織内のユーザーまたはデバイス証明書を必要とする各サービスの要件を収集する必要があります。 この作業を簡単にするために、次のいずれかの計画テンプレートを使用できます。  
 
- [PKCS 証明書テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP 証明書テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fiの要件

エンタープライズ ネットワークに必要なネットワーク構成をデバイスに自動的にWi-Fiするには、新しい構成プロファイルがWi-Fiがあります。 これらのプロファイルをデバイスに展開する Microsoft マネージド デスクトップを構成できます。 ネットワーク セキュリティでデバイスをローカル ドメインの一部にする必要がある場合は、Wi-Fi ネットワーク インフラストラクチャを評価して、Microsoft マネージド デスクトップ デバイスとの互換性を確認する必要がある場合があります (Microsoft マネージド デスクトップ デバイスは Azure AD に参加しているのみ)。 
 
Wi-Fi 構成を Microsoft マネージド デスクトップ デバイスに展開する前に、各デバイス ネットワークに対する組織の要件をWi-Fiがあります。 このアクティビティを簡単にするために、この WiFi プロファイル [テンプレートを使用できます](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)。
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>ワイヤード (有線) 接続要件と 802.1x 認証 
 
デバイスからローカル エリア ネットワーク (LAN) へのアクセスをセキュリティで保護するために 802.1x 認証を使用する場合は、必要な構成の詳細を Microsoft マネージド デスクトップ デバイスにプッシュする必要があります。 Windows 10 バージョン 1809 以降を実行している Microsoft マネージド デスクトップ デバイスは、WiredNetwork 構成サービス プロバイダー (CSP) による 802.1x 構成の展開をサポートしています。 詳細については [、WiredNetwork CSP のドキュメントを参照](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) してください。 
 
ワイヤード (有線) ネットワーク構成プロファイルを Microsoft マネージド デスクトップ デバイスに展開する前に、ワイヤード (有線) 企業ネットワークに関する組織の要件を収集します。 そのために、以下の手順に従ってください。 
 
 
1. 既存の 802.1x プロファイルが構成され、LAN ネットワークに接続されているデバイスにサインオンします。  
2. 管理者の資格情報を使用してコマンド プロンプトを開きます。 
3. netsh インターフェイス表示インターフェイスを実行して LAN **インターフェイス名を検索します**。 
4. netsh lan export profile folder= を実行して LAN プロファイル XML **をエクスポートします。 Interface="interface_name"**. 
5. Microsoft マネージド デスクトップ デバイスでエクスポートしたプロファイルをテストする必要がある場合は **、netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME"** を実行します。 
 
 
## <a name="deploy-certificate-infrastructure"></a>証明書インフラストラクチャを展開する  
 
Intune を使用した既存の SCEP または PKCS インフラストラクチャが既に存在し、このアプローチが要件を満たしている場合は、Microsoft マネージド デスクトップでも使用できます。 SCEP または PKCS インフラストラクチャが既に存在しない場合は、準備する必要があります。  
 
詳細については [、「Microsoft Intune でデバイスの証明書プロファイルを構成する」を参照してください](https://docs.microsoft.com/intune/certificates-configure)。 
 
 
 
## <a name="deploy-a-lan-profile"></a>LAN プロファイルを展開する 
 
LAN プロファイルがエクスポートされた後、次の手順に従って Microsoft マネージド デスクトップのポリシーを準備できます。   
 
1. 次の設定を使用して、LAN プロファイル用に Microsoft Intune でカスタム プロファイルを [作成します (「Intune で Windows 10](https://docs.microsoft.com/intune/custom-settings-windows-10)デバイスのカスタム設定を使用する」を参照してください)。 カスタム **OMA-URI 設定で、[** 追加] **を選択し**、次の値を入力します。 
    - Name: *Modern Workplace-Windows 10 LAN Profile* 
    - 説明: 設定の概要を示す説明と、その他の重要な詳細を入力します。 
    - OMA-URI (大文字と小文字を区別): *「./Device/Vendor/MSFT/WiredNetwork/LanXML」と入力します。*
    - データ型: 文字列 **(XML ファイル) を選択します**。 
    - カスタム XML: エクスポートされた XML ファイルをアップロードします。
2. Microsoft マネージド デスクトップ管理ポータルを使用して Microsoft マネージド デスクトップ IT 運用にサポート要求を送信し、構成プロファイルを確認し、「モダン Workplace Devices – Test」に展開します。 Microsoft マネージド デスクトップ IT 運用では、管理ポータルのサポート要求を通じて、要求が完了した時間を確認できます。
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>証明書と Wi-Fi/VPN プロファイルを展開する 
 
 
証明書とプロファイルを展開するには、次の手順を実行します。

1. ルート証明書と中間証明書ごとにプロファイルを作成します (「信頼された証明書プロファイルの作成 [」を参照してください](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles))。 これらの各プロファイルには、DD/MM/YYYY 形式の有効期限を含む説明が必要です。 **有効期限のない証明書プロファイルは展開されません。**
2. SCEP または PKCS 証明書ごとにプロファイルを作成します [(「SCEP](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) 証明書プロファイルを作成する」または [「PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)証明書プロファイルを作成する」を参照してください)。 これらの各プロファイルには、DD/MM/YYYY 形式の有効期限を含む説明が必要です。 **有効期限のない証明書プロファイルは展開されません。**
3. 企業の WiFi ネットワークごとにプロファイルを作成します (Windows 10 以降のデバイスの[Wi-Fi 設定を参照)。](https://docs.microsoft.com/intune/wi-fi-settings-windows)
4. 企業 VPN ごとにプロファイルを作成します (Intune を使用して VPN 接続を追加するには [、Windows 10 と Windows Holographic のデバイス設定を参照してください](https://docs.microsoft.com/intune/vpn-settings-windows-10))。
5. Microsoft マネージド デスクトップ管理ポータルを使用して、"証明書の展開" または "Wi-Fi プロファイルの展開" というタイトルのサポート要求を Microsoft マネージド デスクトップ IT 運用に提出し、構成プロファイルを確認し、「Modern Workplace Devices – Test」に展開します。 Microsoft マネージド デスクトップ IT 操作は、管理ポータルのサポート要求を通じて要求が完了した時間を知らせします。 
 
 
