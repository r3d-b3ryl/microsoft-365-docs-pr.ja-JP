---
title: Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する
description: 証明書の要件と Wi-Fi 接続
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
audience: Admin
ms.openlocfilehash: a59add6f6821824f189703b3dedd35fda313ec31
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574585"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する  
 
証明書ベースの認証は、Microsoft Managed Desktop を使用しているお客様に共通の要件です。 VPN ソリューションへの接続、または組織内Wi-Fiにアクセスするために、証明書が必要になる場合があります。   
 
Microsoft Managed Desktop デバイスは Azure Active Directory (Azure AD) に参加し、Microsoft Intune によって管理されますので、Intune と統合された簡易証明書登録プロトコル (SCEP) または公開キー暗号化標準 (PKCS) 証明書インフラストラクチャを使用して、このような証明書を展開する必要があります。    
 
## <a name="certificate-requirements"></a>証明書の要件 
 
ルート証明書は、SCEP または PKCS インフラストラクチャを介して証明書を展開するために必要です。 組織内の他のアプリケーションとサービスでは、ルート証明書を Microsoft Managed Desktop デバイスに展開する必要があります。    
 
SCEP または PKCS 証明書を Microsoft Managed Desktop に展開する前に、組織内のユーザーまたはデバイス証明書を必要とする各サービスの要件を収集する必要があります。 このアクティビティを簡単にするために、次のいずれかの計画テンプレートを使用できます。  
 
- [PKCS 証明書テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP 証明書テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fiの要件

エンタープライズ ネットワークに必要な構成をデバイスに自動的にWi-Fiするには、構成プロファイルをWi-Fiがあります。 Microsoft Managed Desktop を構成して、これらのプロファイルをデバイスに展開できます。 ネットワーク セキュリティでデバイスがローカル ドメインの一部である必要がある場合は、Wi-Fi ネットワーク インフラストラクチャを評価して Microsoft Managed Desktop デバイスと互換性を確認する必要があります (Microsoft マネージ デスクトップ デバイスは Azure AD に参加しているのみ)。 
 
Microsoft Managed Desktop デバイスにWi-Fi構成を展開する前に、ネットワークごとに組織の要件をWi-Fiされます。 このアクティビティを簡単にするために、この WiFi プロファイル テンプレート [を使用できます](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)。
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>有線接続要件と 802.1x 認証 
 
802.1x 認証を使用してデバイスからローカル エリア ネットワーク (LAN) へのアクセスをセキュリティで保護する場合は、必要な構成の詳細を Microsoft Managed Desktop デバイスにプッシュする必要があります。 Windows 10 バージョン 1809 以降を実行している Microsoft Managed Desktop デバイスは、WiredNetwork 構成サービス プロバイダー (CSP) を介した 802.1x 構成の展開をサポートします。 詳細については [、「WiredNetwork CSP のドキュメント」を参照](/windows/client-management/mdm/wirednetwork-csp) してください。 
 
Microsoft Managed Desktop デバイスに有線ネットワーク構成プロファイルを展開する前に、組織の有線企業ネットワークの要件を収集してください。 そのために、以下の手順に従ってください。 
 
 
1. 既存の 802.1x プロファイルが構成され、LAN ネットワークに接続されているデバイスにサインオンします。  
2. 管理者資格情報を使用してコマンド プロンプトを開きます。 
3. netsh インターフェイス ショー インターフェイスを実行して **LAN インターフェイス名を検索します**。 
4. netsh lan エクスポート プロファイル フォルダー= を実行して **LAN プロファイル XML をエクスポートします。 Interface="interface_name" .** 
5. Microsoft Managed Desktop デバイスでエクスポートしたプロファイルをテストする必要がある場合は、netsh lan add profile **filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME" を実行します**。 
 
 
## <a name="deploy-certificate-infrastructure"></a>証明書インフラストラクチャの展開  
 
Intune に既存の SCEP または PKCS インフラストラクチャが既に存在し、この方法が要件を満たしている場合は、Microsoft Managed Desktop でも使用できます。 SCEP または PKCS インフラストラクチャが既に存在しない場合は、準備する必要があります。  
 
詳細については [、「Microsoft Intune でデバイスの証明書プロファイルを構成する」を参照してください](/intune/certificates-configure)。 
 
 
 
## <a name="deploy-a-lan-profile"></a>LAN プロファイルの展開 
 
LAN プロファイルをエクスポートしたら、次の手順に従って Microsoft Managed Desktop のポリシーを準備できます。   
 
1. 次の設定を使用して、LAN プロファイルの Microsoft Intune でカスタム プロファイルを作成します (「Intune で [Windows 10](/intune/custom-settings-windows-10)デバイスのカスタム設定を使用する」を参照してください)。 [**カスタム OMA-URI 設定] で、[****追加]** を選択し、次の値を入力します。 
    - 名前: *モダン Workplace-Windows 10 LAN プロファイル* 
    - 説明: 設定の概要、その他の重要な詳細を示す説明を入力します。 
    - OMA-URI (大文字と小文字の区別): *Enter ./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - データ型: [文字列] **(XML ファイル) を選択します**。 
    - カスタム XML: エクスポートされた XML ファイルをアップロードします。
2. Microsoft Managed Desktop Admin ポータルを使用して Microsoft Managed Desktop IT 操作にサポート要求を送信し、構成プロファイルを "モダン ワークプレース デバイス - テスト" に確認して展開します。 Microsoft Managed Desktop IT Operations は、管理ポータルのサポート要求を介して要求が完了した場合に知らせします。
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>証明書と Wi-Fi/VPN プロファイルの展開 
 
 
証明書とプロファイルを展開するには、次の手順を実行します。

1. ルート証明書と中間証明書のそれぞれについてプロファイルを作成します (「信頼できる証明書プロファイルの作成 [」を参照してください](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles)。 これらの各プロファイルには、DD/MM/YYYYY 形式の有効期限を含む説明が必要です。 **有効期限のない証明書プロファイルは展開されません。**
2. SCEP または PKCS 証明書ごとにプロファイルを作成します [(「SCEP](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) 証明書プロファイルを作成する」または [「PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)証明書プロファイルを作成する」を参照) これらの各プロファイルには、DD/MM/YYYY 形式の有効期限を含む説明が必要です。 **有効期限のない証明書プロファイルは展開されません。**
3. 企業の WiFi ネットワークごとにプロファイルを作成します (「Windows 10 以降のデバイスの[Wi-Fi 設定」を参照)。](/intune/wi-fi-settings-windows)
4. 企業 VPN ごとにプロファイルを作成します (Intune を使用して VPN 接続を追加するには [、「Windows 10 と Windows Holographic デバイスの設定」を参照してください](/intune/vpn-settings-windows-10))。
5. Microsoft Managed Desktop Admin ポータルを使用して Microsoft Managed Desktop IT 運用に「証明書の展開」または「Wi-Fi プロファイルの展開」というタイトルのサポート要求を送信し、構成プロファイルを確認し、"モダン Workplace デバイス - テスト" に展開します。 Microsoft Managed Desktop IT Operations は、管理ポータルのサポート要求を介して要求が完了した時間を知らせします。 
 
## <a name="steps-to-get-ready"></a>準備の手順

1. 「Microsoft [Managed Desktop の前提条件」を参照してください](prerequisites.md)。
2. 準備 [状況評価ツールを使用します](readiness-assessment-tool.md)。
3. [ゲスト アカウントの前提条件](guest-accounts.md)
4. [Microsoft マネージド デスクトップのネットワーク構成](network.md)
5. [Microsoft Managed Desktop 用の証明書とネットワーク プロファイルを準備](certs-wifi-lan.md) する (この記事)
6. [Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する](authentication.md)
7. [Microsoft マネージド デスクトップのアプリ](apps.md)
8. [Microsoft マネージド デスクトップ用に、マップされたドライブを準備する](mapped-drives.md)
9. [Microsoft マネージド デスクトップ用に、印刷リソースを準備する](printing.md) 
