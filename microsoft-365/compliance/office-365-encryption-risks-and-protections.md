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
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: この記事では、365 を使用するリスクとOffice保護に使用できる暗号化テクノロジについて学習します。
ms.openlocfilehash: b266e7f556510df7fdd5c9140bbc7666e2aa330c
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/29/2020
ms.locfileid: "49738024"
---
# <a name="encryption-risks-and-protections"></a>暗号化のリスクと保護

Microsoft は、Microsoft 365 サービスおよび顧客データに対するリスクに焦点を当てたコントロールとコンプライアンスのフレームワークに従います。 Microsoft は、これらのリスクを軽減するために、大量のテクノロジとプロセス ベースのメソッド (コントロールと呼ばれます) を実装しています。 コントロールによるリスクの特定、評価、軽減は継続的なプロセスです。 

施設、ネットワーク、サーバー、アプリケーション、ユーザー (Microsoft 管理者など) やデータなど、クラウド サービスのさまざまなレイヤー内にコントロールを実装すると、詳細な防御戦略が形成されます。 この戦略の鍵は、同じまたは同様のリスク シナリオから保護するために、さまざまなコントロールが異なるレイヤーに実装される点です。 この多層的なアプローチでは、何らかの理由でコントロールが失敗した場合に備え、フェールセーフ保護を提供します。

リスク のシナリオと、それらを軽減する現在利用可能な暗号化テクノロジを以下に示します。 これらのシナリオは、多くの場合、Office 365 で実装された他のコントロールによって軽減されます。

| 暗号化テクノロジ | サービス | キー管理 | リスク シナリオ | 値 |
|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BitLocker | Exchange Online、SharePoint Online、Skype for Business | Microsoft | ディスクまたはサーバーが盗まれたり、不適切にリサイクルされた。 | BitLocker は、ハードウェア (サーバー/ディスク) が盗まれたり、不適切にリサイクルされた場合のデータ損失から保護するために、フェールセーフなアプローチを提供します。 |
| サービスの暗号化 | SharePoint Online、Skype for Business、OneDrive for BusinessExchange Online (ロードマップ) | Microsoft | 内部または外部のハッカーは、BLOB として個々のファイル/データにアクセスしようとする。 | 暗号化されたデータは、キーにアクセスせずに解読することはできません。 ハッカーがデータにアクセスするリスクを軽減するのに役立ちます。 |
| 顧客キー | SharePoint Online、OneDrive for Business、Exchange Online、Skype for Business | 顧客 | N/A (この機能はコンプライアンス機能として設計されています。リスクの軽減策として設計された機能ではありません)。 | お客様が内部の規制とコンプライアンスの義務を果たすのに役立ち、サービスを停止して Microsoft のデータへのアクセスを取り消す機能を提供します。 |
| Microsoft 365 とクライアント間の TLS | Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Teams、Yammer | Microsoft、お客様 | インターネット上の Microsoft 365 とクライアント コンピューター間のデータ フローをタップする Man-in-the-middle などの攻撃。 | この実装は、Microsoft と顧客の両方に価値を提供し、Microsoft 365 とクライアントの間を流れるデータの整合性を保証します。 |
| Microsoft データセンター間の TLS | Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business | Microsoft | Man-in-the-middle などの攻撃を行い、異なる Microsoft データセンターにある Microsoft 365 サーバー間の顧客データ フローをタップします。 | この実装は、Microsoft データセンター間の攻撃からデータを保護するもう 1 つの方法です。 |
| Azure Rights Management (Microsoft 365 または Azure Information Protection に含まれています) | Exchange Online、SharePoint Online、OneDrive for Business | 顧客 | データは、データにアクセスしなき人の手に入ります。 | Azure Information Protection は Azure RMS を使用します。これは、暗号化、ID、および承認ポリシーを使用して顧客に価値を提供し、複数のデバイス間でファイルと電子メールを保護するのに役立ちます。 Azure RMS は、特定の条件 (つまり、特定のアドレスへのすべてのメール) に一致する Microsoft 365 からのすべての電子メールを、別の受信者に送信する前に自動的に暗号化できるお客様に価値を提供します。 |
| S/MIME | Exchange Online | 顧客 | 電子メールは、目的の受信者ではない人の手に入ります。 | S/MIME は、S/MIME で暗号化された電子メールを電子メールの直接受信者だけが解読できると保証することで、お客様に価値を提供します。 |
| Office 365 Message Encryption | Exchange Online、SharePoint Online | 顧客 | 保護された添付ファイルを含む電子メールは、電子メールの意図した受信者ではない Microsoft 365 の内または外部のユーザーの手に入ります。 | OME は、特定の条件 (つまり、特定のアドレスへのすべてのメール) に一致する Microsoft 365 からのすべての電子メールが、別の内部または外部の受信者に送信される前に自動的に暗号化される顧客に価値を提供します。 |
| パートナー組織との SMTP TLS | Exchange Online | 顧客 | メールは、Microsoft 365 テナントから別のパートナー組織への転送中に man-in-the-middle などの攻撃によって傍受されます。 | このシナリオは、暗号化された SMTP チャネル内で Microsoft 365 テナントとパートナーの電子メール組織との間ですべての電子メールを送受信できるよう、お客様に価値を提供します。 |

## <a name="encryption-technologies-available-in-multi-tenant-environments"></a>マルチテナント環境で使用可能な暗号化テクノロジ

| 暗号化テクノロジ | 実装者 | 主要な Exchange アルゴリズムと強度 | キー管理\* | FIPS 140-2 Validated |
|----------------------------------------------------------------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 ビット | AES 外部キーは、シークレット セーフと Exchange サーバーのレジストリに格納されます。 シークレット セーフは、アクセスに高レベルの昇格と承認が必要なセキュリティで保護されたリポジトリです。 アクセスは、ロックボックス (Lockbox) という内部ツールを使用する場合にのみ要求および承認できます。 AES 外部キーは、サーバーのトラステッド プラットフォーム モジュールにも格納されます。 48 桁の数値パスワードが Active Directory に格納され、ロックボックスによって保護されます。 | はい |
|  | SharePoint Online | AES 256 ビット | AES 外部キーはシークレット セーフに格納されます。 シークレット セーフは、アクセスに高レベルの昇格と承認が必要なセキュリティで保護されたリポジトリです。 アクセスは、ロックボックス (Lockbox) という内部ツールを使用する場合にのみ要求および承認できます。 AES 外部キーは、サーバーのトラステッド プラットフォーム モジュールにも格納されます。 48 桁の数値パスワードが Active Directory に格納され、ロックボックスによって保護されます。 | 必要 |
|  | Skype for Business | AES 256 ビット | AES 外部キーはシークレット セーフに格納されます。 シークレット セーフは、アクセスに高レベルの昇格と承認が必要なセキュリティで保護されたリポジトリです。 アクセスは、ロックボックス (Lockbox) という内部ツールを使用する場合にのみ要求および承認できます。 AES 外部キーは、サーバーのトラステッド プラットフォーム モジュールにも格納されます。 48 桁の数値パスワードが Active Directory に格納され、ロックボックスによって保護されます。 | 必要 |
| サービスの暗号化 | SharePoint Online | AES 256 ビット | BLOB の暗号化に使用されるキーは、SharePoint Online コンテンツ データベースに格納されます。 SharePoint Online コンテンツ データベースは、データベース アクセス制御と保存中の暗号化によって保護されます。 暗号化は、Azure SQL Database で TDE を使用して実行されます。 これらのシークレットは、テナント レベルではなく SharePoint Online のサービス レベルです。 これらのシークレット (マスター キーとも呼ばれます) は、キー ストアと呼ばれる別のセキュリティで保護されたリポジトリに格納されます。 TDE は、アクティブ データベースとデータベース バックアップとトランザクション ログの両方にセキュリティを提供します。 ユーザーがオプションキーを入力すると、顧客キーは Azure Key Vault に格納され、サービスはそのキーを使用してテナント キーを暗号化します。テナント キーはサイト キーの暗号化に使用され、このキーはファイル レベルキーの暗号化に使用されます。 基本的には、顧客がキーを提供するときに新しいキー階層が導入されます。 | 必要 |
|  | Skype for Business | AES 256 ビット | 各データは、ランダムに生成された異なる 256 ビット キーを使用して暗号化されます。 暗号化キーは、対応するメタデータ XML ファイルに格納され、会議ごとのマスター キーによっても暗号化されます。 また、マスター キーは会議ごとに 1 回ランダムに生成されます。 | はい |
|  | Exchange Online | AES 256 ビット | 各メールボックスは、Microsoft によって制御される暗号化キーを使用するデータ暗号化ポリシー (ロードマップ) または顧客 (顧客キーが使用されている場合) を使用して暗号化されます。 | 必要 |
| Microsoft 365 とクライアント/パートナー間の TLS | Exchange Online | [複数の暗号スイートをサポートする見分け的な TLS](https://technet.microsoft.com/library/mt163898.aspx) | Exchange Online (outlook.office.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> Exchange Online の TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA1RSA 証明書です。 | はい (256 ビット暗号強度を備えた TLS 1.2 を使用する場合) |
|  | SharePoint Online | TLS 1.2 と AES 256 <br> <br> [OneDrive for Business および SharePoint Online におけるデータ暗号化](https://technet.microsoft.com/library/dn905447.aspx) | SharePoint Online (*.sharepoint.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> SharePoint Online の TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA1RSA 証明書です。 | 必要 |
|  | Skype for Business | [SIP 通信および PSOM データ共有セッションの TLS](https://support.office.com/article/Set-up-your-network-for-Skype-for-Business-Online-d21f89b0-3afc-432e-b735-036b2432fdbf) | Skype for Business (*.lync.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> Skype for Business の TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 | はい |
|  | Microsoft Teams | TLS 1.2 と AES 256 <br> <br> [Microsoft Teams に関してよく寄せられる質問 - 管理者向けヘルプ](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft Teams (teams.microsoft.com、edge.skype.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> Microsoft Teams の TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 | 必要 |
| Microsoft データセンター間の TLS | すべての Microsoft 365 サービス | TLS 1.2 と AES 256 <br> <br> セキュア リアルタイム 転送プロトコル (SRTP) | Microsoft は、Microsoft データセンター間のサーバー間通信に、内部で管理および展開された証明機関を使用します。 | 必要 |
| Azure Rights Management (Microsoft 365 または Azure Information Protection に含まれています) | Exchange Online | 更新 [され拡張された](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))RMS 暗号化実装である Cryptographic Mode 2 をサポートします。 署名と暗号化に RSA 2048 をサポートし、署名のハッシュに SHA-256 をサポートします。 | [Microsoft によって管理されます](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | はい |
|  | SharePoint Online | 更新 [され拡張された](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))RMS 暗号化実装である Cryptographic Mode 2 をサポートします。 署名と暗号化に RSA 2048、署名用に SHA-256 をサポートしています。 | [既定の設定である Microsoft](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)によって管理されます。または <br> <br> お客様が管理するキーは、Microsoft によって管理されるキーの代わりに使用されます。 IT で管理される Azure サブスクリプションを持つ組織は、BYOK を使用して追加料金を支払う必要はありません。 詳細については、「Bring [Your Own Key の実装」を参照してください](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 この構成では、キーを保護するために nCipher HSM が使用されます。 詳細については [、nCipher HSM と Azure RMS を参照してください](https://www.thales-esecurity.com/msrms/cloud)。 | はい |
| S/MIME | Exchange Online | Cryptographic Message Syntax Standard 1.5 (PKCS #7) | 展開されている顧客管理の公開キー基盤に依存します。 キー管理は顧客によって実行され、Microsoft は署名と解読に使用される秘密キーにアクセスできません。 | はい (3DES または AES256 で送信メッセージを暗号化するように構成されている場合) |
| Office 365 Message Encryption | Exchange Online | Azure RMS と同じ ( 署名と暗号化のための暗号化モード[2](https://technet.microsoft.com/library/dn569290.aspx) - RSA 2048、署名の場合は SHA-256) | Azure Information Protection を暗号化インフラストラクチャとして使用します。 使用される暗号化方式は、メッセージの暗号化と復号化に使用する RMS キーを取得する場所によって異なります。 | 必要 |
| パートナー組織との SMTP TLS | Exchange Online | TLS 1.2 と AES 256 | Exchange Online (outlook.office.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> Exchange Online の TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA1RSA 証明書です。 | はい (256 ビット暗号強度を備えた TLS 1.2 を使用する場合) |

*\*この表で参照されている TLS 証明書は、米国のデータセンター向けです。米国以外のデータセンターでも、2048 ビットの SHA256RSA 証明書を使用します。*

## <a name="encryption-technologies-available-in-government-cloud-community-environments"></a>政府機関のクラウド コミュニティ環境で利用可能な暗号化テクノロジ

| 暗号化テクノロジ | 実装者 | 主要な Exchange アルゴリズムと強度 | キー管理\* | FIPS 140-2 Validated |
|---------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 ビット | AES 外部キーは、シークレット セーフと Exchange サーバーのレジストリに格納されます。 シークレット セーフは、アクセスに高レベルの昇格と承認が必要なセキュリティで保護されたリポジトリです。 アクセスは、ロックボックス (Lockbox) という内部ツールを使用する場合にのみ要求および承認できます。 AES 外部キーは、サーバーのトラステッド プラットフォーム モジュールにも格納されます。 48 桁の数値パスワードが Active Directory に格納され、ロックボックスによって保護されます。 | はい |
|  | SharePoint Online | AES 256 ビット | AES 外部キーはシークレット セーフに格納されます。 シークレット セーフは、アクセスに高レベルの昇格と承認が必要なセキュリティで保護されたリポジトリです。 アクセスは、ロックボックス (Lockbox) という内部ツールを使用する場合にのみ要求および承認できます。 AES 外部キーは、サーバーのトラステッド プラットフォーム モジュールにも格納されます。 48 桁の数値パスワードが Active Directory に格納され、ロックボックスによって保護されます。 | 必要 |
|  | Skype for Business | AES 256 ビット | AES 外部キーはシークレット セーフに格納されます。 シークレット セーフは、アクセスに高レベルの昇格と承認が必要なセキュリティで保護されたリポジトリです。 アクセスは、ロックボックス (Lockbox) という内部ツールを使用する場合にのみ要求および承認できます。 AES 外部キーは、サーバーのトラステッド プラットフォーム モジュールにも格納されます。 48 桁の数値パスワードが Active Directory に格納され、ロックボックスによって保護されます。 | 必要 |
| サービスの暗号化 | SharePoint Online | AES 256 ビット | BLOB の暗号化に使用されるキーは、SharePoint Online コンテンツ データベースに格納されます。 SharePoint Online コンテンツ データベースは、データベース アクセス制御と保存中の暗号化によって保護されます。 暗号化は、Azure SQL Database で TDE を使用して実行されます。 これらのシークレットは、テナント レベルではなく SharePoint Online のサービス レベルです。 これらのシークレット (マスター キーとも呼ばれます) は、キー ストアと呼ばれる別のセキュリティで保護されたリポジトリに格納されます。 TDE は、アクティブ データベースとデータベース バックアップとトランザクション ログの両方にセキュリティを提供します。 ユーザーがオプションキーを入力すると、顧客キーは Azure Key Vault に格納され、サービスはそのキーを使用してテナント キーを暗号化します。テナント キーはサイト キーの暗号化に使用され、このキーはファイル レベルキーの暗号化に使用されます。 基本的には、顧客がキーを提供するときに新しいキー階層が導入されます。 | 必要 |
|  | Skype for Business | AES 256 ビット | 各データは、ランダムに生成された異なる 256 ビット キーを使用して暗号化されます。 暗号化キーは、対応するメタデータ XML ファイルに格納され、会議ごとのマスター キーによっても暗号化されます。 また、マスター キーは会議ごとに 1 回ランダムに生成されます。 | はい |
|  | Exchange Online | AES 256 ビット | 各メールボックスは、Microsoft によって制御される暗号化キーを使用するデータ暗号化ポリシーを使用するか、顧客が (顧客キーを使用する場合) 暗号化ポリシーを使用して暗号化されます。 | 必要 |
| Microsoft 365 とクライアント/パートナー間の TLS | Exchange Online | [複数の暗号スイートをサポートする見分け的な TLS](https://technet.microsoft.com/library/mt163898.aspx) | Exchange Online (outlook.office.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> Exchange Online の TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA1RSA 証明書です。 | はい (256 ビット暗号強度を備えた TLS 1.2 を使用する場合) |
|  | SharePoint Online | TLS 1.2 と AES 256 | SharePoint Online (*.sharepoint.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> SharePoint Online の TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA1RSA 証明書です。 | 必要 |
|  | Skype for Business | SIP 通信および PSOM データ共有セッションの TLS | Skype for Business (*.lync.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> Skype for Business の TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 | はい |
|  | Microsoft Teams | [Microsoft Teams に関してよく寄せられる質問 - 管理者向けヘルプ](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft Teams (teams.microsoft.com; edge.skype.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> Microsoft Teams の TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 | 必要 |
| Microsoft データセンター間の TLS | Exchange Online、SharePoint Online、Skype for Business | TLS 1.2 と AES 256 | Microsoft は、Microsoft データセンター間のサーバー間通信に、内部で管理および展開された証明機関を使用します。 | 必要 |
|  |  | セキュア リアルタイム 転送プロトコル (SRTP) |  |  |
| Azure Rights Management サービス | Exchange Online | 更新 [され拡張された](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))RMS 暗号化実装である Cryptographic Mode 2 をサポートします。 署名と暗号化に RSA 2048 をサポートし、署名のハッシュに SHA-256 をサポートします。 | [Microsoft によって管理されます](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | はい |
|  | SharePoint Online | 更新 [され拡張された](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))RMS 暗号化実装である Cryptographic Mode 2 をサポートします。 署名と暗号化に RSA 2048 をサポートし、署名のハッシュに SHA-256 をサポートします。 | [既定の設定である Microsoft](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)によって管理されます。または <br> <br> 顧客が管理するキー (BYOK とも呼ばれる) は、Microsoft によって管理されるキーの代わりに使用されます。 IT で管理される Azure サブスクリプションを持つ組織は、BYOK を使用して追加料金を支払う必要はありません。 詳細については、「Bring [Your Own Key の実装」を参照してください](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 <br> <br> BYOK シナリオでは、キーを保護するために nCipher HSM が使用されます。 詳細については [、nCipher HSM と Azure RMS を参照してください](https://www.thales-esecurity.com/msrms/cloud)。 | はい |
| S/MIME | Exchange Online | Cryptographic Message Syntax Standard 1.5 (PKCS #7) | 展開されている公開キー基盤に依存します。 | はい(3DES または AES-256 で送信メッセージを暗号化するように構成されている場合)。 |
| Office 365 Message Encryption | Exchange Online | Azure RMS と同じ ( 署名と暗号化のための暗号化モード[2](https://technet.microsoft.com/library/dn569290.aspx) - RSA 2048、署名内のハッシュの SHA-256) | Azure RMS を暗号化インフラストラクチャとして使用します。 使用される暗号化方式は、メッセージの暗号化と復号化に使用する RMS キーを取得する場所によって異なります。 <br> <br> Microsoft Azure RMS を使用してキーを取得する場合は、暗号化モード 2 が使用されます。 Active Directory (AD) RMS を使用してキーを取得する場合は、暗号化モード 1 または暗号化モード 2 が使用されます。 使用される方法は、社内 AD RMS 展開によって異なります。 暗号化モード 1 は、元来の AD RMS 暗号実装です。 署名と暗号化に RSA 1024 をサポートし、署名用の SHA-1 をサポートします。 このモードは、HSM を使用する BYOK 構成を除き、RMS のすべての現在のバージョンで引き続きサポートされます。 | 必要 |
| パートナー組織との SMTP TLS | Exchange Online | TLS 1.2 と AES 256 | Exchange Online (outlook.office.com) の TLS 証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの SHA256RSA 証明書です。 <br> <br> Exchange Online の TLS ルート証明書は、Baltimore CyberTrust Root によって発行された 2048 ビットの sha1RSA 証明書です。 <br> <br> セキュリティ上の理由から、証明書は時に変わる点に注意してください。 | 必要 |

*\*この表で参照されている TLS 証明書は、米国のデータセンター向けです。米国以外のデータセンターでも、2048 ビットの SHA256RSA 証明書を使用します。*
