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
ms.openlocfilehash: e6c6c6f2e77ef81efae29f98baa85feafada9724cc12623bf1501316a91a38f5
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53819201"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用に証明書とネットワーク プロファイルを準備する  
 
証明書ベースの認証は、証明書を使用しているお客様に共通Microsoft マネージド デスクトップ。 VPN ソリューションへの接続、または組織内Wi-Fiにアクセスするために、証明書が必要になる場合があります。   
 
Microsoft マネージド デスクトップ デバイスは Azure Active Directory (Azure AD) に参加し、Microsoft Intune によって管理されますので、Intune と統合された簡易証明書登録プロトコル (SCEP) または公開キー暗号化標準 (PKCS) 証明書インフラストラクチャを使用して、このような証明書を展開する必要があります。    
 
## <a name="certificate-requirements"></a>証明書の要件 
 
ルート証明書は、SCEP または PKCS インフラストラクチャを介して証明書を展開するために必要です。 組織内の他のアプリケーションとサービスでは、ルート証明書をデバイスに展開する必要Microsoft マネージド デスクトップがあります。    
 
SCEP または PKCS 証明書を Microsoft マネージド デスクトップ に展開する前に、組織内のユーザーまたはデバイス証明書を必要とする各サービスの要件を収集する必要があります。 このアクティビティを簡単にするために、次のいずれかの計画テンプレートを使用できます。  
 
- [PKCS 証明書テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [SCEP 証明書テンプレート](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

  
## <a name="wi-fi-connectivity-requirements"></a>Wi-Fiの要件

エンタープライズ ネットワークに必要な構成をデバイスに自動的にWi-Fiするには、構成プロファイルをWi-Fiがあります。 これらのプロファイルをMicrosoft マネージド デスクトップデバイスに展開する構成を構成できます。 ネットワーク セキュリティでデバイスがローカル ドメインの一部である必要がある場合は、Wi-Fi ネットワーク インフラストラクチャを評価して、Microsoft マネージド デスクトップ デバイス (Microsoft マネージド デスクトップ デバイスは Azure AD 参加のみ) と互換性を保つ必要があります。 
 
デバイスにWi-Fi構成Microsoft マネージド デスクトップする前に、各デバイス ネットワークに対する組織の要件をWi-Fiされます。 このアクティビティを簡単にするために、この WiFi プロファイル テンプレート [を使用できます](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx)。
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>有線接続要件と 802.1x 認証 
 
802.1x 認証を使用してデバイスからローカル エリア ネットワーク (LAN) へのアクセスをセキュリティで保護する場合は、必要な構成の詳細を Microsoft マネージド デスクトップ デバイスにプッシュする必要があります。 Microsoft マネージド デスクトップ以降Windows 10 Version 1809デバイスは、WiredNetwork 構成サービス プロバイダー (CSP) による 802.1x 構成の展開をサポートします。 詳細については [、「WiredNetwork CSP のドキュメント」を参照](/windows/client-management/mdm/wirednetwork-csp) してください。 
 
有線ネットワーク構成プロファイルをデバイスに展開する前Microsoft マネージド デスクトップ、有線企業ネットワークに関する組織の要件を収集します。 そのために、以下の手順に従ってください。 
 
 
1. 既存の 802.1x プロファイルが構成され、LAN ネットワークに接続されているデバイスにサインオンします。  
2. 管理者資格情報を使用してコマンド プロンプトを開きます。 
3. netsh インターフェイス ショー インターフェイスを実行して **LAN インターフェイス名を検索します**。 
4. netsh lan エクスポート プロファイル フォルダー= を実行して **LAN プロファイル XML をエクスポートします。 Interface="interface_name" .** 
5. エクスポートしたプロファイルを Microsoft マネージド デスクトップ デバイスでテストする必要がある場合は **、netsh lan add profile filename="PATH_AND_FILENAME.xml" interface="INTERFACE_NAME" を実行します**。 
 
 
## <a name="deploy-certificate-infrastructure"></a>証明書インフラストラクチャの展開  
 
Intune で既存の SCEP または PKCS インフラストラクチャが既に存在し、この方法が要件を満たしている場合は、このインフラストラクチャを使用して、Microsoft マネージド デスクトップ。 SCEP または PKCS インフラストラクチャが既に存在しない場合は、準備する必要があります。  
 
詳細については、「デバイスの[証明書プロファイルを構成する」](/intune/certificates-configure)を参照Microsoft Intune。 
 
 
 
## <a name="deploy-a-lan-profile"></a>LAN プロファイルの展開 
 
LAN プロファイルをエクスポートしたら、次の手順に従って、Microsoft マネージド デスクトップポリシーを準備できます。   
 
1. 次の設定を使用Microsoft Intune LAN プロファイルのカスタム プロファイルを作成します (「Intune でデバイスのカスタム設定Windows 10使用する」[を参照してください](/intune/custom-settings-windows-10))。 [**カスタム OMA-URI 設定] で、[追加****]** を選択し、次の値を入力します。 
    - 名前: *モダン Workplace-Windows 10 LAN プロファイル* 
    - 説明: 設定の概要、その他の重要な詳細を示す説明を入力します。 
    - OMA-URI (大文字と小文字の区別): *Enter ./Device/Vendor/MSFT/WiredNetwork/LanXML*
    - データ型: [文字列] **(XML ファイル) を選択します**。 
    - カスタム XML: アップロード XML ファイルを作成します。
2. 管理者ポータルを使用Microsoft マネージド デスクトップ IT 運用にサポート要求Microsoft マネージド デスクトップ送信し、構成プロファイルを "モダン ワークプレース デバイス - テスト" に確認して展開します。 Microsoft マネージド デスクトップIT 操作では、管理ポータルのサポート要求を介して要求が完了した時間を知らせた。
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>証明書と Wi-Fi/VPN プロファイルの展開 
 
 
証明書とプロファイルを展開するには、次の手順を実行します。

1. ルート証明書と中間証明書のそれぞれについてプロファイルを作成します (「信頼できる証明書プロファイルの作成 [」を参照してください](/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles)。 これらの各プロファイルには、DD/MM/YYYYY 形式の有効期限を含む説明が必要です。 **有効期限のない証明書プロファイルは展開されません。**
2. SCEP または PKCS 証明書ごとにプロファイルを作成します [(「SCEP](/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) 証明書プロファイルを作成する」または [「PKCS](/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)証明書プロファイルを作成する」を参照) これらの各プロファイルには、DD/MM/YYYY 形式の有効期限を含む説明が必要です。 **有効期限のない証明書プロファイルは展開されません。**
3. 企業の WiFi ネットワークごとにプロファイルを作成します (「Wi-Fi の設定」を参照[)、Windows 10を参照してください](/intune/wi-fi-settings-windows)。
4. 企業 VPN ごとにプロファイルを作成します (Intune を使用して VPN 接続をWindows 10、Windows [Holographic](/intune/vpn-settings-windows-10)デバイスの設定を参照してください)。
5. Microsoft マネージド デスクトップ 管理ポータルを使用して Microsoft マネージド デスクトップ IT 運用に "証明書の展開" または "Wi-Fi プロファイルの展開" というタイトルのサポート要求を送信し、構成プロファイルを確認し、"モダン Workplace デバイス - テスト" に展開します。 Microsoft マネージド デスクトップIT 操作では、管理ポータルのサポート要求を介して要求が完了した時間を知らせた。 
 
## <a name="steps-to-get-ready"></a>準備の手順

1. 詳細については[、「前提条件」をMicrosoft マネージド デスクトップ。](prerequisites.md)
2. 準備 [状況評価ツールを使用します](readiness-assessment-tool.md)。
3. [ゲスト アカウントの前提条件](guest-accounts.md)
4. [Microsoft マネージド デスクトップのネットワーク構成](network.md)
5. [証明書とネットワーク プロファイルをMicrosoft マネージド デスクトップする](certs-wifi-lan.md)(この記事)
6. [Microsoft マネージド デスクトップ用にオンプレミス リソース アクセスを準備する](authentication.md)
7. [Microsoft マネージド デスクトップのアプリ](apps.md)
8. [Microsoft マネージド デスクトップ用に、マップされたドライブを準備する](mapped-drives.md)
9. [Microsoft マネージド デスクトップ用に、印刷リソースを準備する](printing.md) 
