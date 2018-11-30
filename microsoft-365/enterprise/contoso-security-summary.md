---
title: Contoso Corporation 向けの Microsoft 365 Enterprise の概要
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が Microsoft 365 Enterprise 全体でセキュリティ機能を使用している方法について説明します。
ms.openlocfilehash: 2cbabb04c79816684f4c566b92003bb64471d22b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869391"
---
# <a name="summary-of-microsoft-365-enterprise-security-for-the-contoso-corporation"></a>Contoso Corporation 向けの Microsoft 365 Enterprise の概要

**概要:** Contoso 社が Microsoft 365 Enterprise 全体でセキュリティ機能を使用している方法について説明します。

IT セキュリティ部門による Microsoft 365 Enterprise の展開の承認を得るために、徹底的なセキュリティ レビューが実施されました。Contoso 社でのクラウドに対するセキュリティ要件を次に示します。

- クラウド リソースにアクセスする従業員に対して、最も強力な認証方法を使用します
- 必ず PC とモバイル デバイスを接続し、セキュリティで保護された方法でアプリケーションにアクセスします
- PC と電子メールをマルウェアから保護します
- クラウド ベースのデジタル資産のアクセス許可は、アクセス可能なユーザー、アクセスの対象、ユーザーが実行できること、最小限の特権アクセス用にデザインされていることを定義します
- 機密性の高い、厳しく規制されたデジタル資産にはラベルが付けられ、暗号化され、安全な場所に保管されます
- 厳しく規制されたデジタル資産をアクセス許可で保護します
- IT のセキュリティは、中心となるダッシュボードからセキュリティの状況を監視できます。迅速な対応とリスク軽減のために、セキュリティ イベントの通知を受け取ることができます

## <a name="contosos-path-to-microsoft-365-security-readiness"></a>Contoso 社の Microsoft 365 準備完了までのプロセス

Contoso 社は、Microsoft 365 Enterprise の展開用に自社のセキュリティを準備するために、次の手順を行いました。

1. クラウドの管理者アカウントを制限する

   Contoso 社では、既存の Windows Server AD 管理者アカウントの広範なレビューを行い、一連のクラウド管理者アカウントおよびグループを設定しました。

2. データ分析を行い 3 つのレベルに分類する

   Contoso 社は慎重なレビューを行い、3 つのレベルを決定しました。これらのレベルは、Contoso 社の最も重要なデータを保護するための Microsoft 365 Enterprise の機能の決定に使用されました。

3. 各データ レベルに応じてアクセス ポリシー、保持ポリシー、情報保護ポリシーを決定した

   データ レベルに基づき、Contoso 社は詳細な要件を決定しました。これらの要件は、クラウドに移動する将来の IT ワークロードを制限するために使用されます。

セキュリティのベスト プラクティスと Microsoft 365 Enterprise 展開の要件に基づき、Contoso 社のセキュリティ管理者と IT 部門は次のセクションに示すように、数多くのセキュリティ機能を展開しました。

## <a name="identity--access-management"></a>ID およびアクセス管理 

- MFA および PIM を設定した全体管理者専用アカウント

  Contoso 社では、日常的に使うユーザー アカウントに全体管理者ロールを割り当てるのではなく、非常に強力なパスワードを設定した全体管理者専用アカウントを 3 つ作成し、それらを多要素認証 (MFA) と Azure AD Privileged Identity Management (PIM) で保護しました。 

  全体管理者アカウントでサインインするのは特定の管理タスクを実行するときのみで、パスワードは指定されたスタッフにのみ知らされています。パスワードは Azure AD PIM で設定された時間内にのみ使用できます。 

  Contoso 社のセキュリティ管理者は、IT 担当者の職務と責任に従って、各アカウントに一部の管理者ロールを割り当てました。

  詳細については、「[Office 365 の管理者の役割](https://support.office.com/article/about-office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)」を参照してください。

- すべてのユーザー アカウントの MFA

  MFA を使用すると、サインイン プロセスの保護の層が厚くなり、パスワードを正しく入力した後、ユーザーに対して、電話、テキスト メッセージ、スマートフォンのアプリ通知のいずれかを通して確認が求められます。MFA を使用すれば、アカウント パスワードが漏えいした場合であっても、Azure AD ユーザー アカウントは承認されていないサインイン イベントから保護されます。

   - Contoso 社では、Microsoft 365 サブスクリプションが危害を受けるのを防ぐため、すべての全体管理者アカウントで MFA を有効にしました。
   - 組織内の信頼されている人の資格情報が漏えいし、攻撃者が悪意のある電子メールを送信するというフィッシング攻撃からの保護を目的として、Contoso 社ではマネージャーや経営幹部を含むすべてのユーザー アカウントで MFA を有効にしました。 

- 条件付きアクセス ポリシーを使用したデバイスとアプリケーションへの安全なアクセス

  Contoso 社では、ID、デバイス、Exchange Online、および SharePoint Online に[条件付きアクセス ポリシー](microsoft-365-policies-configurations.md)を使用しています。ID の条件付きアクセス ポリシーには、リスクの高いユーザーに対するパスワード変更の要求や、クライアントに対する最新の認証をサポートしていないアプリの使用禁止が含まれます。デバイスの条件付きポリシーには、承認されたアプリを定義することや、準拠している PC とモバイル デバイスが必要になることが含まれます。Exchange Online の条件付きアクセス ポリシーには、ActiveSync クライアントのブロックと、Office 365 のメッセージ暗号化の設定が含まれます。SharePoint Online の条件付きアクセス ポリシーには、機密性の高い厳しく規制されたサイトに対する追加の保護が含まれます。

- Windows Hello for Business

  Contoso 社では、Windows 10 Enterprise を実行している PC とモバイル デバイスで強力な 2 要素認証を使用するパスワードの必要性を最終的に解消するために、[Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) を導入済みで、必須になっています。

- Windows Defender Credential Guard

  管理者特権を使用してオペレーティング システムで実行されている標的型の攻撃やマルウェアをブロックするために、Contoso 社では Windows Server AD グループ ポリシーを通じて [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) を有効にしています。

## <a name="threat-protection"></a>脅威保護

- Windows Defender ウイルス対策を使用したマルウェアからの保護

  Contoso 社では、Windows 10 Enterprise を実行する PC とデバイスのマルウェア対策およびマルウェア対策の管理に [Windows Defender ウイルス対策](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)を使用しています。

- Office 365 Advanced Threat Protection を使用した安全な電子メールのフローとメールボックス監査ログ 

  Contoso 社では、電子メール経由で送信される不明なマルウェア、ウイルス、悪意のある URL からの保護を目的として、Exchange Online Protection と [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) を使用しています。 

  Contoso 社では、メールボックス監査ログを有効にして、ユーザーのメールボックスにログインしてメッセージを送信したのはだれかや、メールボックス所有者、委任ユーザー、管理者が実行した他の操作を判別しています。

- Office 365 脅威インテリジェンスを使用した攻撃の監視と防止

  Contoso 社では、[Office 365 脅威インテリジェンス](https://docs.microsoft.com/office365/securitycompliance/office-365-ti)を使用して攻撃の特定と対処を容易にし、将来の攻撃を防ぐことで、Office 365 ユーザーを保護します。

- Advanced Threat Analytics を使用した高度な攻撃からの保護

  Contoso 社では、[Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) を使用して高度な標的型の攻撃から自社を保護しています。ATA は自動的に、正常および異常なエンティティ (ユーザー、デバイス、およびリソース) の動作を分析、学習、識別します。 

## <a name="information-protection"></a>情報保護

- Azure Information Protection を使用した機密性の高い厳しく規制されたデジタル資産の保護

  Contoso 社では 3 レベルのデータ保護を決定し、ユーザーがデジタル資産に適用する [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection) ラベルを展開しました。企業秘密やその他の知的財産について、Contoso 社では、コンテンツを暗号化し特定のセキュリティグループへのアクセスを制限する厳しく規制されたデータに対して、範囲を限定したポリシーで Azure Information Protection サブラベルを使用します。

- Office 365 データ損失防止機能を使用したイントラネット データの漏洩防止

  Contoso 社では、Exchange Online、SharePoint Online、および OneDrive for Business 用に[データ損失防止](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)ポリシーを構成し、故意か偶然かを問わずユーザーが機密データを共有することがないようにしています。

- デバイスのデータ漏洩を防止する Windows 情報保護

  Contoso 社では [Windows 情報保護 (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) を使用して、インターネットベースのアプリとサービス、企業が所有するデバイスと従業員が仕事に携帯するデバイス上のエンタープライズ アプリとデータからデータが漏洩しないよう保護しています。

- Microsoft Cloud App Security を使用したクラウドの監視

  Contoso 社では [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) を使用して、自社のクラウド環境のマップ、使用状況を監視、セキュリティ イベントとインシデントの検出を行っています。 

- Office 365 Cloud App Security を使用した Office 365 のセキュリティの監視

  Contoso 社のセキュリティ管理者は [Office 365 Cloud App Security (CAS)](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview) を使用して警告をセットアップし、SharePoint Online や OneDrive for Business からの大量のデータのダウンロード、サインインしようとして繰り返される失敗、不明なまたは危険な IP アドレスからのサインインなど、通常とは異なるユーザー動作や危険なユーザー動作があると通知が行われるようにします。

- Microsoft Intune を使用したデバイス管理

  Enterprise Management + Security (EMS) スイートの一部として、Contoso 社では [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) を使用して、モバイル デバイスとその上で実行されるアプリへのアクセスを登録、管理、構成します。デバイスベースの条件付きアクセス ポリシーには、承認されたアプリと、準拠している PC とモバイル デバイスも必要です。

## <a name="security-management"></a>セキュリティ管理

- Azure Security Center を使用した中心となる IT 用のセキュリティ ダッシュボード

  Contoso 社では [Azure Security Center](https://docs.microsoft.com/intune/introduction-intune) を使用して、セキュリティと脅威の保護を一元的に把握し、ワークロード全体でセキュリティ ポリシーを管理して、サイバー攻撃に対処しています。

- Windows Defender セキュリティ センターを使用したユーザー向けの中心となるセキュリティ ダッシュボード

  Contoso 社では [Windows Defender セキュリティ センターのアプリ](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)を、Windows 10 Enterprise を実行する自社の PC およびデバイスに展開しました。これにより、ユーザーはセキュリティの状況を一目で把握し、対応策を講じることができます。


## <a name="next-step"></a>次の手順

Cotoso 社が社内の研究チーム間で共同作業を行えるようにするために、厳しく規制されたデータに対応した SharePoint Online サイトを作成した方法について[学習](contoso-sharepoint-online-site-for-highly-confidential-assets.md)します。

