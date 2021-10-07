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
description: この記事では、セキュリティ保護に対するリスクとOffice 365暗号化テクノロジについて学習します。
ms.openlocfilehash: fc1792c11bfbe0451eb2a835b3b02504ab05546f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190667"
---
# <a name="encryption-risks-and-protections"></a>暗号化のリスクと保護

Microsoft は、サービスおよび顧客データに対するリスクに焦点を当てたMicrosoft 365コンプライアンス フレームワークに従います。 Microsoft では、これらのリスクを軽減するために、大規模なテクノロジとプロセス ベースのメソッド (コントロールと呼ばれます) を実装しています。 コントロールによるリスクの識別、評価、軽減は、継続的なプロセスです。 

施設、ネットワーク、サーバー、アプリケーション、ユーザー (Microsoft 管理者など)、データなど、クラウド サービスのさまざまな層内でのコントロールの実装は、詳細な防御戦略を形成します。 この戦略の重要なポイントは、同じまたは同様のリスク シナリオから保護するために、さまざまなコントロールが異なる層に実装される点です。 この多層的なアプローチは、何らかの理由でコントロールが失敗した場合に備え、フェールセーフ保護を提供します。

一部のリスク シナリオと、それらを軽減する現在利用可能な暗号化テクノロジを以下に示します。 これらのシナリオは、多くの場合、その他のコントロールを使用して軽減され、Office 365。

| 暗号化テクノロジ | サービス | キー管理 | リスク シナリオ | 値 |
|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BitLocker | Exchange Online、SharePointオンライン、および Skype for Business | Microsoft | ディスクまたはサーバーが盗まれたり、不適切にリサイクルされた場合。 | BitLocker は、盗まれたハードウェアまたは不適切にリサイクルされたハードウェア (サーバー/ディスク) によるデータの損失から保護するためのフェールセーフアプローチを提供します。 |
| サービスの暗号化 | SharePointオンライン、Skype for Business、およびOneDrive for Business。Exchange Online (ロードマップ) | Microsoft | 内部または外部のハッカーは、BLOB として個々のファイル/データにアクセスします。 | 暗号化されたデータは、キーにアクセスせずに復号化できません。 ハッカーがデータにアクセスするリスクを軽減するのに役立ちます。 |
| 顧客キー | SharePointオンライン、OneDrive for Business、Exchange Online、およびSkype for Business | 顧客 | N/A (この機能はコンプライアンス機能として設計されています。リスクの軽減策として設計されています)。 | お客様が内部の規制とコンプライアンスの義務を果たすのを助け、サービスを離れ、Microsoft のデータへのアクセスを取り消す機能 |
| クライアントとクライアントMicrosoft 365 TLS | Exchange Online、SharePoint、OneDrive for Business、Skype for Business、Teams、およびYammer | Microsoft、カスタマー | インターネットを使用してユーザーとクライアント コンピューターの間のデータ フローをタップする中間者攻撃Microsoft 365攻撃。 | この実装は、Microsoft と顧客の両方に価値を提供し、ユーザーとクライアントの間を流れるデータMicrosoft 365保証します。 |
| Microsoft データセンター間の TLS | Exchange Online、SharePoint、オンライン、OneDrive for Business、およびSkype for Business | Microsoft | 中間者または他の攻撃を実行して、異なる Microsoft データセンターにMicrosoft 365サーバー間の顧客データ フローをタップします。 | この実装は、Microsoft データセンター間の攻撃からデータを保護するもう 1 つの方法です。 |
| Azure Rights Management (Microsoft 365または Azure Information Protection に含まれる) | Exchange Online、SharePointオンライン、およびOneDrive for Business | 顧客 | データは、データにアクセスできない人の手に入ります。 | Azure Information Protection は Azure RMS を使用し、暗号化、ID、および承認ポリシーを使用して顧客に価値を提供し、複数のデバイス間でファイルと電子メールをセキュリティで保護します。 Azure RMS は、特定の条件に一致する Microsoft 365 から発信されるすべての電子メール (つまり、特定のアドレスへのすべての電子メール) を、別の受信者に送信する前に自動的に暗号化できる顧客に価値を提供します。 |
| S/MIME | Exchange Online | 顧客 | 電子メールは、目的の受信者ではない人の手に当たります。 | S/MIME は、S/MIME で暗号化された電子メールが電子メールの直接受信者によってのみ解読できると保証することで、顧客に価値を提供します。 |
| Office 365 Message Encryption | Exchange Online, SharePoint Online | 顧客 | 保護された添付ファイルを含む電子メールは、電子メールの目的の受信者ではないMicrosoft 365または外部のユーザーの手に入ります。 | OME は、特定の条件に一致する Microsoft 365 から発信された電子メール (つまり、特定のアドレスへのすべての電子メール) が、別の内部または外部受信者に送信される前に自動的に暗号化される顧客に価値を提供します。 |
| パートナー組織との SMTP TLS | Exchange Online | 顧客 | メールは、ネットワーク テナントから別のパートナー組織への転送中に、中間者または他の攻撃Microsoft 365傍受されます。 | このシナリオは、暗号化された SMTP チャネル内の Microsoft 365 テナントとパートナーの電子メール組織との間ですべての電子メールを送受信できるよう、顧客に価値を提供します。 |

## <a name="encryption-technologies-available-in-multi-tenant-environments"></a>マルチテナント環境で使用できる暗号化テクノロジ

| 暗号化テクノロジ | 実装者 | 主要なExchangeアルゴリズムと強さ | キー管理\* | FIPS 140-2 検証済み |
|----------------------------------------------------------------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 ビット | AES 外部キーは、シークレット サーバーとセーフサーバーのレジストリにExchangeされます。 Secret セーフは、アクセスに高レベルの昇格と承認が必要なセキュリティで保護されたリポジトリです。 アクセスは、ロックボックスと呼ばれる内部ツールを使用してのみ要求および承認できます。 AES 外部キーは、サーバーの信頼済みプラットフォーム モジュールにも格納されます。 48 桁の数値パスワードは Active Directory に格納され、ロックボックスによって保護されます。 | はい |
|  | SharePoint Online | AES 256 ビット | AES 外部キーはシークレット キーにセーフ。 Secret セーフは、アクセスに高レベルの昇格と承認が必要なセキュリティで保護されたリポジトリです。 アクセスは、ロックボックスと呼ばれる内部ツールを使用してのみ要求および承認できます。 AES 外部キーは、サーバーの信頼済みプラットフォーム モジュールにも格納されます。 48 桁の数値パスワードは Active Directory に格納され、ロックボックスによって保護されます。 | はい |
|  | Skype for Business | AES 256 ビット | AES 外部キーはシークレット キーにセーフ。 Secret セーフは、アクセスに高レベルの昇格と承認が必要なセキュリティで保護されたリポジトリです。 アクセスは、ロックボックスと呼ばれる内部ツールを使用してのみ要求および承認できます。 AES 外部キーは、サーバーの信頼済みプラットフォーム モジュールにも格納されます。 48 桁の数値パスワードは Active Directory に格納され、ロックボックスによって保護されます。 | はい |
| サービスの暗号化 | SharePoint Online | AES 256 ビット | BLOB の暗号化に使用されるキーは、オンライン コンテンツ データベースSharePoint格納されます。 オンライン SharePointデータベースは、保存時にデータベース アクセス制御と暗号化によって保護されます。 暗号化は、TDE を使用してAzure SQL Database。 これらのシークレットは、テナント レベルではなく、SharePoint Online のサービス レベルです。 これらのシークレット (マスター キーとも呼ばれます) は、キー ストアと呼ばれる別のセキュリティで保護されたリポジトリに格納されます。 TDE は、アクティブ なデータベースとデータベースのバックアップとトランザクション ログの両方にセキュリティを提供します。 ユーザーがオプションのキーを指定すると、顧客キーは Azure Key Vault に格納され、サービスはキーを使用してテナント キーを暗号化し、サイト キーを暗号化するために使用され、ファイル レベルのキーを暗号化するために使用されます。 基本的に、顧客がキーを提供するときに新しいキー階層が導入されます。 | はい |
|  | Skype for Business | AES 256 ビット | データの各部分は、異なるランダムに生成された 256 ビット キーを使用して暗号化されます。 暗号化キーは、対応するメタデータ XML ファイルに格納され、会議ごとのマスター キーによっても暗号化されます。 マスター キーは、会議ごとに 1 回ランダムに生成されます。 | はい |
|  | Exchange Online | AES 256 ビット | 各メールボックスは、Microsoft が制御する暗号化キー (ロードマップ上) または顧客 (顧客キーが使用されている場合) を使用するデータ暗号化ポリシーを使用して暗号化されます。 | はい |
| クライアントとMicrosoft 365パートナー間の TLS | Exchange Online | [複数の暗号スイートをサポートする日和見 TLS](./exchange-online-uses-tls-to-secure-email-connections.md) | Exchange Online (outlook.office.com) の TLS 証明書は、ボルチモア CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> この証明書の TLS ルートExchange Onlineは、ボルチモア サイバートラスト ルートによって発行された 2048 ビットの SHA1RSA 証明書です。 | はい、256 ビットの暗号強度を持つ TLS 1.2 が使用されている場合 |
|  | SharePoint Online | TLS 1.2 と AES 256 <br> <br> [OneDrive for Business および SharePoint Online におけるデータ暗号化](./data-encryption-in-odb-and-spo.md) | SharePoint Online (*.sharepoint.com) の TLS 証明書は、ボルチモア サイバートラスト ルートによって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> SharePoint Online の TLS ルート証明書は、ボルチモア サイバートラスト ルートによって発行された 2048 ビットの SHA1RSA 証明書です。 | はい |
|  | Skype for Business | [SIP 通信および PSOM データ共有セッションの TLS](https://support.office.com/article/Set-up-your-network-for-Skype-for-Business-Online-d21f89b0-3afc-432e-b735-036b2432fdbf) | Skype for Business (*.lync.com) の TLS 証明書は、ボルチモア CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> この証明書の TLS ルートSkype for Businessは、ボルチモア サイバートラスト ルートによって発行された 2048 ビットの SHA256RSA 証明書です。 | はい |
|  | Microsoft Teams | TLS 1.2 と AES 256 <br> <br> [ユーザーに関するよくある質問 - Microsoft Teamsヘルプ](/MicrosoftTeams/teams-overview) | Microsoft Teams (teams.microsoft.com、edge.skype.com) の TLS 証明書は、ボルチモア サイバートラスト ルートによって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> この証明書の TLS ルートMicrosoft Teamsは、ボルチモア サイバートラスト ルートによって発行された 2048 ビットの SHA256RSA 証明書です。 | はい |
| Microsoft データセンター間の TLS | すべてのMicrosoft 365サービス | TLS 1.2 と AES 256 <br> <br> セキュリティで保護されたリアルタイム トランスポート プロトコル (SRTP) | Microsoft は、Microsoft データセンター間のサーバー間通信に内部管理および展開された証明機関を使用します。 | はい |
| Azure Rights Management (Microsoft 365または Azure Information Protection に含まれる) | Exchange Online | 暗号化 [モード 2 、](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))更新された拡張 RMS 暗号化実装をサポートします。 署名と暗号化に対して RSA 2048、署名のハッシュに SHA-256 をサポートします。 | [Microsoft によって管理されます](/azure/information-protection/plan-implement-tenant-key)。 | はい |
|  | SharePoint Online | 暗号化 [モード 2 、](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))更新された拡張 RMS 暗号化実装をサポートします。 署名と暗号化では RSA 2048、署名には SHA-256 がサポートされています。 | [既定の設定である Microsoft](/azure/information-protection/plan-implement-tenant-key)によって管理されます。または <br> <br> Microsoft が管理するキーに代わる顧客管理。 IT 管理 Azure サブスクリプションを持つ組織では、BYOK を使用し、その使用状況を無料でログに記録できます。 詳細については、「独自のキー [を持ち込む実装」を参照してください](/azure/information-protection/plan-implement-tenant-key)。 この構成では、キーを保護するために nCipher HSM が使用されます。 詳細については [、「nCipher HSM」および「Azure RMS」を参照してください](https://www.thales-esecurity.com/msrms/cloud)。 | はい |
| S/MIME | Exchange Online | 暗号化メッセージ構文標準 1.5 (PKCS #7) | 展開されている顧客管理の公開キー インフラストラクチャによって異なります。 キー管理は顧客によって実行され、Microsoft は署名と復号化に使用される秘密キーにアクセスできません。 | はい、3DES または AES256 で送信メッセージを暗号化するように構成されている場合 |
| Office 365 Message Encryption | Exchange Online | Azure RMS と同じ (署名と暗号化の場合は暗号化モード[2](./technical-reference-details-about-encryption.md) - RSA 2048、署名の場合は SHA-256) | Azure Information Protection を暗号化インフラストラクチャとして使用します。 使用される暗号化方式は、メッセージの暗号化と復号化に使用する RMS キーを取得する場所によって異なります。 | はい |
| パートナー組織との SMTP TLS | Exchange Online | TLS 1.2 と AES 256 | Exchange Online (outlook.office.com) の TLS 証明書は、DigiCert Cloud Services CA-1 によって発行された RSA 暗号化証明書を使用した 2048 ビットの SHA-256 です。 <br> <br> この証明書の TLS ルートExchange Onlineは、GlobalSign ルート CA – R1 によって発行された RSA 暗号化証明書を持つ 2048 ビット[の SHA-1 です](./exchange-online-uses-tls-to-secure-email-connections.md#tls-certificate-information-for-exchange-online)。 <br> <br> セキュリティ上の理由から、証明書は変更される場合があります。 | はい、256 ビットの暗号強度を持つ TLS 1.2 が使用されている場合 |

*\*この表で参照されている TLS 証明書は、米国のデータセンター向けです。米国以外のデータセンターでは、2048 ビットの SHA256RSA 証明書も使用されます。*

## <a name="encryption-technologies-available-in-government-cloud-community-environments"></a>政府機関のクラウド コミュニティ環境で利用できる暗号化テクノロジ

| 暗号化テクノロジ | 実装者 | 主要なExchangeアルゴリズムと強さ | キー管理\* | FIPS 140-2 検証済み |
|---------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 ビット | AES 外部キーは、シークレット サーバーとセーフサーバーのレジストリにExchangeされます。 Secret セーフは、アクセスに高レベルの昇格と承認が必要なセキュリティで保護されたリポジトリです。 アクセスは、ロックボックスと呼ばれる内部ツールを使用してのみ要求および承認できます。 AES 外部キーは、サーバーの信頼済みプラットフォーム モジュールにも格納されます。 48 桁の数値パスワードは Active Directory に格納され、ロックボックスによって保護されます。 | はい |
|  | SharePoint Online | AES 256 ビット | AES 外部キーはシークレット キーにセーフ。 Secret セーフは、アクセスに高レベルの昇格と承認が必要なセキュリティで保護されたリポジトリです。 アクセスは、ロックボックスと呼ばれる内部ツールを使用してのみ要求および承認できます。 AES 外部キーは、サーバーの信頼済みプラットフォーム モジュールにも格納されます。 48 桁の数値パスワードは Active Directory に格納され、ロックボックスによって保護されます。 | はい |
|  | Skype for Business | AES 256 ビット | AES 外部キーはシークレット キーにセーフ。 Secret セーフは、アクセスに高レベルの昇格と承認が必要なセキュリティで保護されたリポジトリです。 アクセスは、ロックボックスと呼ばれる内部ツールを使用してのみ要求および承認できます。 AES 外部キーは、サーバーの信頼済みプラットフォーム モジュールにも格納されます。 48 桁の数値パスワードは Active Directory に格納され、ロックボックスによって保護されます。 | はい |
| サービスの暗号化 | SharePoint Online | AES 256 ビット | BLOB の暗号化に使用されるキーは、オンライン コンテンツ データベースSharePoint格納されます。 オンライン SharePointデータベースは、保存時のデータベース アクセス制御と暗号化によって保護されます。 暗号化は、TDE を使用してAzure SQL Database。 これらのシークレットは、テナント レベルではなく、SharePoint Online のサービス レベルです。 これらのシークレット (マスター キーとも呼ばれます) は、キー ストアと呼ばれる別のセキュリティで保護されたリポジトリに格納されます。 TDE は、アクティブ なデータベースとデータベースのバックアップとトランザクション ログの両方にセキュリティを提供します。 ユーザーがオプションのキーを指定すると、顧客キーは Azure Key Vault に格納され、サービスはキーを使用してテナント キーを暗号化し、サイト キーの暗号化に使用され、ファイル レベルのキーの暗号化に使用されます。 基本的に、顧客がキーを提供するときに新しいキー階層が導入されます。 | はい |
|  | Skype for Business | AES 256 ビット | データの各部分は、異なるランダムに生成された 256 ビット キーを使用して暗号化されます。 暗号化キーは、対応するメタデータ XML ファイルに格納され、会議ごとのマスター キーによっても暗号化されます。 マスター キーは、会議ごとに 1 回ランダムに生成されます。 | はい |
|  | Exchange Online | AES 256 ビット | 各メールボックスは、Microsoft または顧客が制御する暗号化キーを使用するデータ暗号化ポリシーを使用して暗号化されます (顧客キーを使用する場合)。 | はい |
| クライアントとMicrosoft 365パートナー間の TLS | Exchange Online | [複数の暗号スイートをサポートする日和見 TLS](./exchange-online-uses-tls-to-secure-email-connections.md) | Exchange Online (outlook.office.com) の TLS 証明書は、ボルチモア CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> この証明書の TLS ルートExchange Onlineは、ボルチモア サイバートラスト ルートによって発行された 2048 ビットの SHA1RSA 証明書です。 | はい、256 ビットの暗号強度を持つ TLS 1.2 が使用されている場合 |
|  | SharePoint Online | TLS 1.2 と AES 256 | SharePoint Online (*.sharepoint.com) の TLS 証明書は、ボルチモア サイバートラスト ルートによって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> SharePoint Online の TLS ルート証明書は、ボルチモア サイバートラスト ルートによって発行された 2048 ビットの SHA1RSA 証明書です。 | はい |
|  | Skype for Business | SIP 通信および PSOM データ共有セッションの TLS | Skype for Business (*.lync.com) の TLS 証明書は、ボルチモア CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> この証明書の TLS ルートSkype for Businessは、ボルチモア サイバートラスト ルートによって発行された 2048 ビットの SHA256RSA 証明書です。 | はい |
|  | Microsoft Teams | [ユーザーに関するよくある質問 - Microsoft Teamsヘルプ](/MicrosoftTeams/teams-overview) | Microsoft Teams (teams.microsoft.com; edge.skype.com) の TLS 証明書は、ボルチモア サイバートラスト ルートによって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> この証明書の TLS ルートMicrosoft Teamsは、ボルチモア サイバートラスト ルートによって発行された 2048 ビットの SHA256RSA 証明書です。 | はい |
| Microsoft データセンター間の TLS | Exchange Online, SharePoint, Skype for Business | TLS 1.2 と AES 256 | Microsoft は、Microsoft データセンター間のサーバー間通信に内部管理および展開された証明機関を使用します。 | はい |
|  |  | セキュリティで保護されたリアルタイム トランスポート プロトコル (SRTP) |  |  |
| Azure Rights Management Service | Exchange Online | 暗号化 [モード 2 、](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))更新された拡張 RMS 暗号化実装をサポートします。 署名と暗号化に対して RSA 2048、署名のハッシュに SHA-256 をサポートします。 | [Microsoft によって管理されます](/azure/information-protection/plan-implement-tenant-key)。 | はい |
|  | SharePoint Online | 暗号化 [モード 2 、](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))更新された拡張 RMS 暗号化実装をサポートします。 署名と暗号化に対して RSA 2048、署名のハッシュに SHA-256 をサポートします。 | [既定の設定である Microsoft](/azure/information-protection/plan-implement-tenant-key)によって管理されます。または <br> <br> Microsoft が管理するキーの代わりに、顧客が管理する (BYOK とも呼ばれる)。 IT 管理 Azure サブスクリプションを持つ組織では、BYOK を使用し、その使用状況を無料でログに記録できます。 詳細については、「独自のキー [を持ち込む実装」を参照してください](/azure/information-protection/plan-implement-tenant-key)。 <br> <br> BYOK シナリオでは、キーを保護するために nCipher HSM が使用されます。 詳細については [、「nCipher HSM」および「Azure RMS」を参照してください](https://www.thales-esecurity.com/msrms/cloud)。 | はい |
| S/MIME | Exchange Online | 暗号化メッセージ構文標準 1.5 (PKCS #7) | 展開されている公開キー インフラストラクチャによって異なります。 | はい、3DES または AES-256 で送信メッセージを暗号化するように構成されている場合。 |
| Office 365 Message Encryption | Exchange Online | Azure RMS と同じ (署名と暗号化の場合は暗号化モード[2](./technical-reference-details-about-encryption.md) - RSA 2048、署名のハッシュでは SHA-256) | 暗号化インフラストラクチャとして Azure RMS を使用します。 使用される暗号化方式は、メッセージの暗号化と復号化に使用する RMS キーを取得する場所によって異なります。 <br> <br> RMS を使用Microsoft Azureキーを取得する場合は、暗号化モード 2 が使用されます。 Active Directory (AD) RMS を使用してキーを取得する場合は、暗号化モード 1 または暗号化モード 2 が使用されます。 使用される方法は、社内 AD RMS 展開によって異なります。 暗号化モード 1 は、元来の AD RMS 暗号実装です。 署名と暗号化に対して RSA 1024 をサポートし、署名用の SHA-1 をサポートします。 このモードは、HSM を使用する BYOK 構成を除く、現在のすべてのバージョンの RMS で引き続きサポートされます。 | はい |
| パートナー組織との SMTP TLS | Exchange Online | TLS 1.2 と AES 256 | Exchange Online (outlook.office.com) の TLS 証明書は、DigiCert Cloud Services CA-1 によって発行された RSA 暗号化証明書を使用した 2048 ビットの SHA-256 です。 <br> <br> この証明書の TLS ルートExchange Onlineは、GlobalSign ルート CA – R1 によって発行された RSA 暗号化証明書を持つ 2048 ビット[の SHA-1 です](./exchange-online-uses-tls-to-secure-email-connections.md#tls-certificate-information-for-exchange-online)。 <br> <br> セキュリティ上の理由から、証明書は変更される場合があります。 | はい、256 ビットの暗号強度を持つ TLS 1.2 が使用されている場合 |

*\*この表で参照されている TLS 証明書は、米国のデータセンター向けです。米国以外のデータセンターでは、2048 ビットの SHA256RSA 証明書も使用されます。*