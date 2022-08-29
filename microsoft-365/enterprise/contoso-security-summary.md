---
title: Contoso Corporation のエンタープライズ セキュリティに関する Microsoft 365 の概要
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso がエンタープライズ向けに Microsoft 365 のセキュリティ機能を使用する方法。
ms.openlocfilehash: 46611f5321c893466448b39a9990501d9b3fafc2
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67385465"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Contoso Corporation のエンタープライズ セキュリティに関する Microsoft 365 の概要

エンタープライズ向けの Microsoft 365 を展開するための承認を得るために、Contoso IT セキュリティ部門は徹底的なセキュリティ レビューを実施しました。 クラウドに対する次のセキュリティ要件を特定しました。

- 従業員がクラウド リソースにアクセスするには、最も強力な認証方法を使用します。
- PC とモバイル デバイスが安全な方法でアプリケーションに接続してアクセスすることを確認します。
- PC と電子メールをマルウェアから保護します。
- クラウドベースのデジタル資産に対するアクセス許可は、だれが何を行うことができるかを定義し、最小特権アクセス用に設計されています
- 機密性が高く、規制の厳しいデジタル資産は、ラベル付け、暗号化、およびセキュリティで保護された場所に格納されます。
- 高度に規制されたデジタル資産は、追加の暗号化とアクセス許可で保護されます。
- IT セキュリティ スタッフは、中央ダッシュボードから現在のセキュリティ体制を監視し、迅速な対応と軽減策のためにセキュリティ イベントの通知を受け取ることができます。

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Microsoft 365 セキュリティの準備への Contoso パス

Contoso は次の手順に従って、エンタープライズ向けの Microsoft 365 を展開するためのセキュリティを準備しました。

1. クラウドの管理者アカウントを制限する

   Contoso は、既存のActive Directory Domain Services (AD DS) 管理者アカウントの詳細なレビューを行い、一連の専用クラウド管理者アカウントとグループを設定しました。

2. データを 3 つのセキュリティ レベルに分類する

   Contoso は注意深くレビューを行い、3 つのレベルを決定しました。これは、最も貴重なデータを保護するためにエンタープライズ機能用の Microsoft 365 を識別するために使用されました。

3. 各データ レベルについてアクセス、保持、情報保護ポリシーを決定する

   Contoso は、データ レベルに基づいて、クラウドに移行される将来の IT ワークロードを評価するための詳細な要件を決定しました。

Contoso のセキュリティ管理者とその IT 部門は、セキュリティのベスト プラクティスと Microsoft 365 に従って、次のセクションで説明するように多くのセキュリティ機能を展開しました。

## <a name="identity-and-access-management"></a>ID およびアクセス管理 

- MFA および PIM を設定した全体管理者専用アカウント

  Contoso は、毎日のユーザー アカウントにグローバル管理者ロールを割り当てるのではなく、強力なパスワードを持つ 3 つの専用グローバル管理者アカウントを作成しました。 アカウントは、Azure AD Multi-Factor Authentication (MFA) と Azure Active Directory (Azure AD) Privileged Identity Management (PIM) によって保護されます。 *PIM は、Microsoft 365 E5 でのみ使用可能です。*

  **Azure AD DC 管理者** または **グローバル管理者** アカウントを使用したサインインは、特定の管理タスクに対してのみ行われます。 パスワードは指定されたスタッフにのみ認識され、Azure AD PIM で構成された期間内にのみ使用できます。

  Contoso セキュリティ管理者は、IT ワーカーのジョブ機能に適したアカウントに、より少ない管理者ロールを割り当てた。

  詳細については、「[Microsoft 365 の管理者の役割](/office365/admin/add-users/about-admin-roles)」を参照してください。

- すべてのユーザー アカウントの MFA

  MFA により、サインイン プロセスに保護のレイヤーが追加されます。 パスワードを正しく入力した後、スマートフォンで電話、テキスト メッセージ、またはアプリの通知を確認する必要があります。 MFA を使用すると、アカウント のパスワードが侵害された場合でも、Azure AD ユーザー アカウントは承認されていないサインインから保護されます。

   - Microsoft 365 サブスクリプションの侵害から保護するために、Contoso はすべての **Azure AD DC 管理者** または **グローバル管理者** アカウントで MFA を必要とします。
   - 組織内の信頼されている人の資格情報が漏えいし、攻撃者が悪意のある電子メールを送信するというフィッシング攻撃からの保護を目的として、Contoso 社ではマネージャーや経営幹部を含むすべてのユーザー アカウントで MFA を有効にしました。

- 条件付きアクセス ポリシーを使用したデバイスとアプリケーションへの安全なアクセス

  Contoso 社では、ID、デバイス、Exchange Online、および SharePoint に[条件付きアクセス ポリシー](../security/office-365-security/microsoft-365-policies-configurations.md)を使用しています。ID の条件付きアクセス ポリシーには、リスクの高いユーザーに対するパスワード変更の要求や、クライアントに対する最新の認証をサポートしていないアプリの使用禁止が含まれます。デバイスのポリシーには、承認されたアプリを定義することや、準拠している PC とモバイル デバイスが必要になることが含まれます。Exchange Online の条件付きアクセス ポリシーには、ActiveSync クライアントのブロックと、Office 365 のメッセージ暗号化の設定が含まれます。SharePoint の条件付きアクセス ポリシーには、機密性の高い厳しく規制されたサイトに対する追加の保護が含まれます。

- Windows Hello for Business

  Contoso は[、](/windows/security/identity-protection/hello-for-business/hello-identity-verification)Windows 10 Enterpriseを実行している PC とモバイル デバイスでの強力な 2 要素認証を通じて、最終的にパスワードの必要性を排除するためにWindows Hello for Businessを展開しました。

- Windows Defender Credential Guard

  管理者特権を持つオペレーティング システムで実行されているターゲット攻撃やマルウェアをブロックするために、Contoso は AD DS グループ ポリシー[を使用してWindows Defender Credential Guard](/windows/security/identity-protection/credential-guard/credential-guard) を有効にしました。

## <a name="threat-protection"></a>脅威に対する保護

- Microsoft Defender ウイルス対策によるマルウェアからの保護

  Contoso は、Windows 10 Enterpriseを実行している PC とデバイスのマルウェア保護とマルウェア対策管理に [Microsoft Defender ウイルス対策](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)を使用しています。

- Microsoft Defender for Office 365を使用して電子メール フローとメールボックス監査ログをセキュリティで保護する 

  Contoso は、Exchange Online Protectionと[Defender for Office 365](/office365/securitycompliance/office-365-atp)を使用して、電子メールを介して送信される未知のマルウェア、ウイルス、悪意のある URL から保護しています。

  また、Contoso はメールボックス監査ログを有効にして、ユーザー メールボックスにログインするユーザーを特定し、メッセージを送信し、メールボックスの所有者、委任されたユーザー、または管理者が実行するその他のアクティビティを実行しました。

- Office 365 脅威の調査および対応を使用した攻撃の監視と防止

  Contoso は[Office 365脅威の調査と対応](/office365/securitycompliance/office-365-ti)を使用して、攻撃の識別と対処を容易にし、将来の攻撃を防ぐことでユーザーを保護します。

- Advanced Threat Analytics を使用した高度な攻撃からの保護

  Contoso 社では、[Advanced Threat Analytics (ATA)](/advanced-threat-analytics/what-is-ata) を使用して高度な標的型の攻撃から自社を保護しています。ATA は自動的に、正常および異常なエンティティ (ユーザー、デバイス、およびリソース) の動作を分析、学習、識別します。

## <a name="information-protection"></a>情報保護

- Azure Information Protection ラベルを使用した機密性の高い厳しく規制されたデジタル資産の保護

  Contoso は 3 つのレベルのデータ保護を決定し、ユーザーがデジタル資産に適用する [Microsoft 365 秘密度ラベル](../compliance/sensitivity-labels.md) を展開しました。 Contoso は、営業秘密やその他の知的財産について、厳しく規制されたデータに対して機密サブラベルを使用します。 このプロセスでは、コンテンツが暗号化され、特定のユーザー アカウントとグループへのアクセスが制限されます。

- データ損失防止機能を使用したイントラネット データの漏洩防止

  Contoso は[、ユーザーが](../compliance/dlp-learn-about-dlp.md)機密データを誤って、または意図的に共有するのを防ぐために、Exchange Online、SharePoint、およびOneDrive for BusinessのMicrosoft Purview データ損失防止 ポリシーを構成しました。

- デバイスのデータ漏洩を防止する Windows 情報保護

  Contoso は[、Windows Information Protection (WIP)](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) を使用して、インターネット ベースのアプリとサービス、エンタープライズ アプリ、および従業員が仕事に持ち込む企業所有のデバイスや個人用デバイス上のデータを通じたデータ漏えいから保護しています。

- Microsoft Defender for Cloud Appsを使用したクラウド監視

  Contoso は[、Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)を使用してクラウド環境をマップし、その使用状況を監視し、セキュリティ イベントとインシデントを検出しています。 *Microsoft Defender for Cloud AppsはMicrosoft 365 E5でのみ使用できます。*

- Microsoft Intune を使用したデバイス管理

  Contoso 社では [Microsoft Intune](/intune/introduction-intune) を使用して、モバイル デバイスとその上で実行されるアプリへのアクセスを登録、管理、構成します。デバイスベースの条件付きアクセス ポリシーには、承認されたアプリと、準拠している PC とモバイル デバイスも必要です。

## <a name="security-management"></a>セキュリティ管理

- Microsoft Defender for Cloud を使用した IT の中央セキュリティ ダッシュボード

  Contoso は [、Microsoft Defender for Cloud](https://azure.microsoft.com/services/security-center/) を使用して、セキュリティと脅威の保護の統一されたビューを提示し、ワークロード全体のセキュリティ ポリシーを管理し、サイバー攻撃に対応します。

- Windows Defender セキュリティ センターを使用したユーザー向けの中心となるセキュリティ ダッシュボード

  Contoso は[、Windows 10 Enterprise](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)を実行している PC とデバイスにWindows セキュリティ アプリを展開し、ユーザーが自分のセキュリティ体制を一目で確認し、アクションを実行できるようにしました。
