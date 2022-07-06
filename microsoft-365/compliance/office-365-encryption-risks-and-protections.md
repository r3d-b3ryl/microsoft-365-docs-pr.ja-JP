---
title: 暗号化のリスクと保護
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: この記事では、Office 365に対するリスクと、保護に使用できる暗号化テクノロジについて説明します。
ms.openlocfilehash: 3e57ac67506320d549b0ff3208c6763b046367bb
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66635175"
---
# <a name="encryption-risks-and-protections"></a>暗号化のリスクと保護

Microsoft は、Microsoft 365 サービスと顧客データに対するリスクに焦点を当てた制御およびコンプライアンス フレームワークに従います。 Microsoft では、これらのリスクを軽減するために、大量のテクノロジとプロセスベースのメソッド (コントロールと呼ばれます) を実装しています。 コントロールを使用したリスクの識別、評価、軽減は、継続的なプロセスです。 

施設、ネットワーク、サーバー、アプリケーション、ユーザー (Microsoft 管理者など) やデータなど、クラウド サービスのさまざまなレイヤー内での制御の実装は、多層防御戦略を形成します。 この戦略の重要な点は、同じまたは類似のリスク シナリオから保護するために、さまざまなレイヤーにさまざまなコントロールが実装されていることです。 この多層アプローチは、何らかの理由で制御が失敗した場合に備えて、フェールセーフ保護を提供します。

リスクシナリオと、それらを軽減する現在利用可能な暗号化テクノロジの一部を以下に示します。 これらのシナリオは、多くの場合、Office 365に実装されている他のコントロールを使用して軽減されます。

| 暗号化テクノロジ | サービス | キー管理 | リスク シナリオ | 値 |
|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BitLocker | Exchange Online、SharePoint Online、およびSkype for Business | Microsoft | ディスクまたはサーバーが盗まれたり、不適切にリサイクルされたりします。 | BitLocker は、ハードウェア (サーバー/ディスク) の盗難や不適切なリサイクルによるデータの損失から保護するためのフェールセーフなアプローチを提供します。 |
| サービスの暗号化 | SharePoint Online、Skype for Business、OneDrive for Business;Exchange Online | Microsoft | 内部または外部のハッカーは、個々のファイル/データに BLOB としてアクセスしようとします。 | 暗号化されたデータは、キーにアクセスしないと暗号化を解除できません。 ハッカーがデータにアクセスするリスクを軽減するのに役立ちます。 |
| 顧客キー | SharePoint Online、OneDrive for Business、Exchange Online、Skype for Business | 顧客 | N/A (この機能はコンプライアンス機能として設計されており、リスクの軽減策ではありません)。 | お客様が社内の規制とコンプライアンスの義務を満たし、サービスを終了し、Microsoft のデータへのアクセスを取り消す機能を満たすのに役立ちます |
| Microsoft 365 とクライアント間の TLS | Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Teams、Yammer | Microsoft、顧客 | インターネット経由で Microsoft 365 とクライアント コンピューター間のデータ フローをタップするための中間者攻撃またはその他の攻撃。 | この実装は、Microsoft と顧客の両方に価値を提供し、Microsoft 365 とクライアントの間を流れるデータの整合性を保証します。 |
| Microsoft データセンター間の TLS | Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business | Microsoft | 中間者攻撃またはその他の攻撃により、さまざまな Microsoft データセンターにある Microsoft 365 サーバー間の顧客データ フローをタップします。 | この実装は、Microsoft データセンター間の攻撃からデータを保護するもう 1 つの方法です。 |
| Azure Rights Management (Microsoft 365 または Azure Information Protectionに含まれる) | Exchange Online、SharePoint Online、およびOneDrive for Business | 顧客 | データは、データにアクセスできないユーザーの手に渡ります。 | Azure Information Protectionでは、暗号化、ID、承認ポリシーを使用して顧客に価値を提供する Azure RMS を使用して、複数のデバイス間でファイルと電子メールをセキュリティで保護します。 Azure RMS は、特定の条件に一致する Microsoft 365 から送信されたすべての電子メール (つまり、特定のアドレスへのすべてのメール) を、別の受信者に送信する前に自動的に暗号化できる顧客に価値を提供します。 |
| S/MIME | Exchange Online | 顧客 | 電子メールは、目的の受信者ではないユーザーの手に渡ります。 | S/MIME は、S/MIME で暗号化された電子メールを電子メールの直接の受信者のみが復号化できることを保証することで、顧客に価値を提供します。 |
| Office 365 Message Encryption | Exchange Online、SharePoint Online | 顧客 | 保護された添付ファイルを含む電子メールは、電子メールの意図した受信者ではない Microsoft 365 内または外部のユーザーの手に渡ります。 | OME は、特定の条件に一致する Microsoft 365 から送信されたすべての電子メール (つまり、特定のアドレスへのすべてのメール) が、別の内部または外部の受信者に送信される前に自動的に暗号化される顧客に価値を提供します。 |
| パートナー組織との SMTP TLS | Exchange Online | 顧客 | メールは、Microsoft 365 テナントから別のパートナー組織への転送中に中間者攻撃またはその他の攻撃によって傍受されます。 | このシナリオは、Microsoft 365 テナントと、暗号化された SMTP チャネル内のパートナーの電子メール組織との間ですべての電子メールを送受信できるように、顧客に価値を提供します。 |

## <a name="encryption-technologies-available-in-multi-tenant-environments"></a>マルチテナント環境で使用できる暗号化テクノロジ

| 暗号化テクノロジ | によって実装される | Key Exchange アルゴリズムと強度 | キー管理\* | FIPS 140-2 検証済み |
|----------------------------------------------------------------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 ビット | AES 外部キーは、シークレット セーフと Exchange サーバーのレジストリに格納されます。 Secret Safe は、アクセスに高度な昇格と承認を必要とするセキュリティで保護されたリポジトリです。 アクセスは、Lockbox という内部ツールを使用してのみ要求および承認できます。 AES 外部キーは、サーバーのトラステッド プラットフォーム モジュールにも格納されます。 48 桁の数値パスワードは Active Directory に格納され、Lockbox によって保護されます。 | はい |
|  | SharePoint Online | AES 256 ビット | AES 外部キーはシークレット セーフに格納されます。 Secret Safe は、アクセスに高度な昇格と承認を必要とするセキュリティで保護されたリポジトリです。 アクセスは、Lockbox という内部ツールを使用してのみ要求および承認できます。 AES 外部キーは、サーバーのトラステッド プラットフォーム モジュールにも格納されます。 48 桁の数値パスワードは Active Directory に格納され、Lockbox によって保護されます。 | はい |
|  | Skype for Business | AES 256 ビット | AES 外部キーはシークレット セーフに格納されます。 Secret Safe は、アクセスに高度な昇格と承認を必要とするセキュリティで保護されたリポジトリです。 アクセスは、Lockbox という内部ツールを使用してのみ要求および承認できます。 AES 外部キーは、サーバーのトラステッド プラットフォーム モジュールにも格納されます。 48 桁の数値パスワードは Active Directory に格納され、Lockbox によって保護されます。 | はい |
| サービス暗号化 | SharePoint Online | AES 256 ビット | BLOB の暗号化に使用されるキーは、SharePoint Online コンテンツ データベースに格納されます。 SharePoint Online コンテンツ データベースは、データベース アクセス制御と保存時の暗号化によって保護されます。 暗号化は、Azure SQL データベースの TDE を使用して実行されます。 これらのシークレットは、テナント レベルではなく、SharePoint Online のサービス レベルにあります。 これらのシークレット (マスター キーとも呼ばれます) は、キー ストアと呼ばれる別のセキュリティで保護されたリポジトリに格納されます。 TDE は、アクティブなデータベースとデータベースのバックアップとトランザクション ログの両方に保存時のセキュリティを提供します。 お客様が省略可能なキーを指定すると、顧客キーは Azure Key Vaultに格納され、サービスはキーを使用してテナント キーを暗号化します。このキーを使用してサイト キーを暗号化し、それを使用してファイル レベル キーを暗号化します。 基本的に、顧客がキーを提供したときに新しいキー階層が導入されます。 | はい |
|  | Skype for Business | AES 256 ビット | 各データは、異なるランダムに生成された 256 ビット キーを使用して暗号化されます。 暗号化キーは、対応するメタデータ XML ファイルに格納されます。また、会議ごとのマスター キーによっても暗号化されます。 マスター キーも、会議ごとに 1 回ランダムに生成されます。 | はい |
|  | Exchange Online | AES 256 ビット | 各メールボックスは、Microsoft によって制御される暗号化キーを使用するデータ暗号化ポリシー (ロードマップ上) または顧客 (顧客キーが使用されている場合) を使用して暗号化されます。 | はい |
| Microsoft 365 とクライアント/パートナー間の TLS | Exchange Online | [複数の暗号スイートをサポートする日和見 TLS](./exchange-online-uses-tls-to-secure-email-connections.md) | Exchange Online (outlook.office.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA256RSA 証明書です。 <br> <br> Exchange Onlineの TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA1RSA 証明書です。 | はい。TLS 1.2 と 256 ビットの暗号強度が使用されている場合 |
|  | SharePoint Online | AES 256 を使用した TLS 1.2 <br> <br> [OneDrive for Business および SharePoint Online におけるデータ暗号化](./data-encryption-in-odb-and-spo.md) | SharePoint Online (*.sharepoint.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA256RSA 証明書です。 <br> <br> SharePoint Online の TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA1RSA 証明書です。 | はい |
|  | Skype for Business | [SIP 通信と PSOM データ共有セッションの TLS](https://support.office.com/article/Set-up-your-network-for-Skype-for-Business-Online-d21f89b0-3afc-432e-b735-036b2432fdbf) | Skype for Business (*.lync.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA256RSA 証明書です。 <br> <br> Skype for Businessの TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA256RSA 証明書です。 | はい |
|  | Microsoft Teams | AES 256 を使用した TLS 1.2 <br> <br> [Microsoft Teams に関してよく寄せられる質問 - 管理 ヘルプ](/MicrosoftTeams/teams-overview) | Microsoft Teams の TLS 証明書 (teams.microsoft.com、edge.skype.com) は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA256RSA 証明書です。 <br> <br> Microsoft Teams の TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA256RSA 証明書です。 | はい |
| Microsoft データセンター間の TLS | すべての Microsoft 365 サービス | AES 256 を使用した TLS 1.2 <br> <br> セキュリティで保護されたリアルタイム トランスポート プロトコル (SRTP) | Microsoft は、Microsoft データセンター間のサーバー間通信に、内部的に管理および展開された証明機関を使用します。 | はい |
| Azure Rights Management (Microsoft 365 または Azure Information Protectionに含まれる) | Exchange Online | [暗号化モード 2](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)) は、更新され強化された RMS 暗号化実装をサポートします。 署名と暗号化では RSA 2048、署名のハッシュには SHA-256 がサポートされます。 | [Microsoft によって管理されます](/azure/information-protection/plan-implement-tenant-key)。 | はい |
|  | SharePoint Online | [暗号化モード 2](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)) は、更新され強化された RMS 暗号化実装をサポートします。 署名と暗号化では RSA 2048、署名には SHA-256 がサポートされます。 | [既定の設定である Microsoft によって管理](/azure/information-protection/plan-implement-tenant-key)されます。または <br> <br> Microsoft マネージド キーの代替手段であるカスタマー マネージド。 IT マネージド Azure サブスクリプションを持つ組織は、BYOK を使用し、追加料金なしでその使用状況をログに記録できます。 詳細については、「 [独自のキーの実装」を](/azure/information-protection/plan-implement-tenant-key)参照してください。 この構成では、キーを保護するために nCipher HSM が使用されます。 詳細については、「 [nCipher HSM と Azure RMS」を](https://www.thales-esecurity.com/msrms/cloud)参照してください。 | はい |
| S/MIME | Exchange Online | 暗号化メッセージ構文 Standard 1.5 (PKCS #7) | デプロイされたカスタマー マネージドの公開キー インフラストラクチャによって異なります。 キー管理は顧客によって実行され、Microsoft は署名と復号化に使用される秘密キーにアクセスすることはありません。 | はい。3DES または AES256 で送信メッセージを暗号化するように構成されている場合 |
| Office 365 Message Encryption | Exchange Online | Azure RMS と同じ ([暗号化モード 2](./technical-reference-details-about-encryption.md) - 署名と暗号化用の RSA 2048、署名用の SHA-256) | 暗号化インフラストラクチャとして Azure Information Protectionを使用します。 使用される暗号化方式は、メッセージの暗号化と復号化に使用する RMS キーを取得する場所によって異なります。 | はい |
| パートナー組織との SMTP TLS | Exchange Online | AES 256 を使用した TLS 1.2 | Exchange Online (outlook.office.com) の TLS 証明書は、DigiCert Cloud Services CA-1 によって発行された RSA 暗号化証明書を持つ 2048 ビット SHA-256 です。 <br> <br> Exchange Onlineの TLS ルート証明書は、[GlobalSign Root CA – R1](./exchange-online-uses-tls-to-secure-email-connections.md) によって発行された RSA 暗号化証明書を持つ 2048 ビット SHA-1 です。 <br> <br> セキュリティ上の理由から、証明書は随時変更されます。 | はい。TLS 1.2 と 256 ビットの暗号強度が使用されている場合 |

*\*この表で参照されている TLS 証明書は、米国のデータセンター向けです。米国以外のデータセンターでは、2048 ビットの SHA256RSA 証明書も使用されます。*

## <a name="encryption-technologies-available-in-government-cloud-community-environments"></a>Government クラウド コミュニティ環境で利用できる暗号化テクノロジ

| 暗号化テクノロジ | によって実装される | Key Exchange アルゴリズムと強度 | キー管理\* | FIPS 140-2 検証済み |
|---------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 ビット | AES 外部キーは、シークレット セーフと Exchange サーバーのレジストリに格納されます。 Secret Safe は、アクセスに高度な昇格と承認を必要とするセキュリティで保護されたリポジトリです。 アクセスは、Lockbox という内部ツールを使用してのみ要求および承認できます。 AES 外部キーは、サーバーのトラステッド プラットフォーム モジュールにも格納されます。 48 桁の数値パスワードは Active Directory に格納され、Lockbox によって保護されます。 | はい |
|  | SharePoint Online | AES 256 ビット | AES 外部キーはシークレット セーフに格納されます。 Secret Safe は、アクセスに高度な昇格と承認を必要とするセキュリティで保護されたリポジトリです。 アクセスは、Lockbox という内部ツールを使用してのみ要求および承認できます。 AES 外部キーは、サーバーのトラステッド プラットフォーム モジュールにも格納されます。 48 桁の数値パスワードは Active Directory に格納され、Lockbox によって保護されます。 | はい |
|  | Skype for Business | AES 256 ビット | AES 外部キーはシークレット セーフに格納されます。 Secret Safe は、アクセスに高度な昇格と承認を必要とするセキュリティで保護されたリポジトリです。 アクセスは、Lockbox という内部ツールを使用してのみ要求および承認できます。 AES 外部キーは、サーバーのトラステッド プラットフォーム モジュールにも格納されます。 48 桁の数値パスワードは Active Directory に格納され、Lockbox によって保護されます。 | はい |
| サービス暗号化 | SharePoint Online | AES 256 ビット | BLOB の暗号化に使用されるキーは、SharePoint Online コンテンツ データベースに格納されます。 SharePoint Online コンテンツ データベースは、データベース アクセス制御と保存時の暗号化によって保護されます。 暗号化は、Azure SQL データベースの TDE を使用して実行されます。 これらのシークレットは、テナント レベルではなく、SharePoint Online のサービス レベルにあります。 これらのシークレット (マスター キーとも呼ばれます) は、キー ストアと呼ばれる別のセキュリティで保護されたリポジトリに格納されます。 TDE は、アクティブなデータベースとデータベースのバックアップとトランザクション ログの両方に保存時のセキュリティを提供します。 お客様がオプション キーを指定すると、カスタマー キーは Azure Key Vaultに格納され、サービスはキーを使用してテナント キーを暗号化します。このキーは、サイト キーの暗号化に使用され、ファイル レベル キーの暗号化に使用されます。 基本的に、顧客がキーを提供したときに新しいキー階層が導入されます。 | はい |
|  | Skype for Business | AES 256 ビット | 各データは、異なるランダムに生成された 256 ビット キーを使用して暗号化されます。 暗号化キーは、対応するメタデータ XML ファイルに格納されます。また、会議ごとのマスター キーによっても暗号化されます。 マスター キーも、会議ごとに 1 回ランダムに生成されます。 | はい |
|  | Exchange Online | AES 256 ビット | 各メールボックスは、Microsoft または顧客が制御する暗号化キーを使用するデータ暗号化ポリシーを使用して暗号化されます (Customer Key が使用されている場合)。 | はい |
| Microsoft 365 とクライアント/パートナー間の TLS | Exchange Online | [複数の暗号スイートをサポートする日和見 TLS](./exchange-online-uses-tls-to-secure-email-connections.md) | Exchange Online (outlook.office.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA256RSA 証明書です。 <br> <br> Exchange Onlineの TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA1RSA 証明書です。 | はい。TLS 1.2 と 256 ビットの暗号強度が使用されている場合 |
|  | SharePoint Online | AES 256 を使用した TLS 1.2 | SharePoint Online (*.sharepoint.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA256RSA 証明書です。 <br> <br> SharePoint Online の TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA1RSA 証明書です。 | はい |
|  | Skype for Business | SIP 通信と PSOM データ共有セッションの TLS | Skype for Business (*.lync.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA256RSA 証明書です。 <br> <br> Skype for Businessの TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA256RSA 証明書です。 | はい |
|  | Microsoft Teams | [Microsoft Teams に関してよく寄せられる質問 - 管理 ヘルプ](/MicrosoftTeams/teams-overview) | Microsoft Teams (teams.microsoft.com; edge.skype.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA256RSA 証明書です。 <br> <br> Microsoft Teams の TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビット SHA256RSA 証明書です。 | はい |
| Microsoft データセンター間の TLS | Exchange Online、SharePoint Online、Skype for Business | AES 256 を使用した TLS 1.2 | Microsoft は、Microsoft データセンター間のサーバー間通信に、内部的に管理および展開された証明機関を使用します。 | はい |
|  |  | セキュリティで保護されたリアルタイム トランスポート プロトコル (SRTP) |  |  |
| Azure Rights Management Service | Exchange Online | [暗号化モード 2](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)) は、更新され強化された RMS 暗号化実装をサポートします。 署名と暗号化では RSA 2048、署名のハッシュには SHA-256 がサポートされます。 | [Microsoft によって管理されます](/azure/information-protection/plan-implement-tenant-key)。 | はい |
|  | SharePoint Online | [暗号化モード 2](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)) は、更新され強化された RMS 暗号化実装をサポートします。 署名と暗号化では RSA 2048、署名のハッシュには SHA-256 がサポートされます。 | [既定の設定である Microsoft によって管理](/azure/information-protection/plan-implement-tenant-key)されます。または <br> <br> カスタマー マネージド (BYOK とも呼ばれます) は、Microsoft マネージド キーの代替手段です。 IT マネージド Azure サブスクリプションを持つ組織は、BYOK を使用し、追加料金なしでその使用状況をログに記録できます。 詳細については、「 [独自のキーの実装」を](/azure/information-protection/plan-implement-tenant-key)参照してください。 <br> <br> BYOK シナリオでは、キーを保護するために nCipher HSM が使用されます。 詳細については、「 [nCipher HSM と Azure RMS」を](https://www.thales-esecurity.com/msrms/cloud)参照してください。 | はい |
| S/MIME | Exchange Online | 暗号化メッセージ構文 Standard 1.5 (PKCS #7) | デプロイされた公開キー インフラストラクチャによって異なります。 | はい。3DES または AES-256 で送信メッセージを暗号化するように構成されている場合。 |
| Office 365 Message Encryption | Exchange Online | Azure RMS と同じ (署名と暗号化の[暗号化モード 2](./technical-reference-details-about-encryption.md) - RSA 2048、署名のハッシュ用 SHA-256) | 暗号化インフラストラクチャとして Azure RMS を使用します。 使用される暗号化方式は、メッセージの暗号化と復号化に使用する RMS キーを取得する場所によって異なります。 <br> <br> Microsoft Azure RMS を使用してキーを取得する場合は、暗号化モード 2 が使用されます。 Active Directory (AD) RMS を使用してキーを取得する場合は、暗号化モード 1 または暗号化モード 2 が使用されます。 使用される方法は、社内 AD RMS 展開によって異なります。 暗号化モード 1 は、元来の AD RMS 暗号実装です。 署名と暗号化に RSA 1024 をサポートし、署名用の SHA-1 をサポートします。 このモードは、HSM を使用する BYOK 構成を除き、現在のすべてのバージョンの RMS で引き続きサポートされます。 | はい |
| パートナー組織との SMTP TLS | Exchange Online | AES 256 を使用した TLS 1.2 | Exchange Online (outlook.office.com) の TLS 証明書は、DigiCert Cloud Services CA-1 によって発行された RSA 暗号化証明書を持つ 2048 ビット SHA-256 です。 <br> <br> Exchange Onlineの TLS ルート証明書は、[GlobalSign Root CA – R1](./exchange-online-uses-tls-to-secure-email-connections.md) によって発行された RSA 暗号化証明書を持つ 2048 ビット SHA-1 です。 <br> <br> セキュリティ上の理由から、証明書は随時変更されます。 | はい。TLS 1.2 と 256 ビットの暗号強度が使用されている場合 |

*\*この表で参照されている TLS 証明書は、米国のデータセンター向けです。米国以外のデータセンターでは、2048 ビットの SHA256RSA 証明書も使用されます。*
