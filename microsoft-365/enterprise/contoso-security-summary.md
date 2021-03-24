---
title: Contoso Corporation のエンタープライズ セキュリティ向け Microsoft 365 の概要
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso がエンタープライズ向け Microsoft 365 のセキュリティ機能を使用する方法。
ms.openlocfilehash: 1bcbaad2409df81121a92e8ad01f794ae28d8dc6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051486"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Contoso Corporation のエンタープライズ セキュリティ向け Microsoft 365 の概要

Microsoft 365 for enterprise を展開する承認を得るに当たって、Contoso IT セキュリティ部門は徹底的なセキュリティ レビューを実施しました。 クラウドの次のセキュリティ要件を特定しました。

- 従業員がクラウド リソースにアクセスするには、最も強力な認証方法を使用します。
- PC とモバイル デバイスが安全な方法でアプリケーションに接続してアクセスする必要があります。
- PC と電子メールをマルウェアから保護します。
- クラウドベースのデジタル資産に対するアクセス許可は、誰が何にアクセスできるのか、何を実行できるのかを定義し、最小特権アクセス用に設計されています。
- 機密性の高い高度に規制されたデジタル資産は、ラベル付けされ、暗号化され、安全な場所に保存されます。
- 高度に規制されたデジタル資産は、追加の暗号化とアクセス許可で保護されます。
- IT セキュリティ スタッフは、中央ダッシュボードから現在のセキュリティ態勢を監視し、迅速な対応と軽減のためにセキュリティ イベントの通知を受け取ります。

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Microsoft 365 セキュリティ準備への Contoso パス

Contoso 社は、エンタープライズ向け Microsoft 365 の展開に向けてセキュリティを準備するために、次の手順に従いました。

1. クラウドの管理者アカウントを制限する

   Contoso 社は、既存の Active Directory ドメイン サービス (AD DS) 管理者アカウントの詳細なレビューを行い、一連の専用クラウド管理者アカウントとグループを設定しました。

2. データを 3 つのセキュリティ レベルに分類する

   Contoso 社は、最も価値の高いデータを保護するために Microsoft 365 のエンタープライズ機能を特定するために使用された 3 つのレベルを慎重に検討し、決定しました。

3. 各データ レベルについてアクセス、保持、情報保護ポリシーを決定する

   データ レベルに基づいて、Contoso はクラウドに移動される将来の IT ワークロードを修飾する詳細な要件を決定しました。

エンタープライズ展開要件に関するセキュリティのベスト プラクティスと Microsoft 365 に従って、Contoso のセキュリティ管理者とその IT 部門は、次のセクションで説明するように、多くのセキュリティ機能と機能を展開しました。

## <a name="identity-and-access-management"></a>ID およびアクセス管理 

- MFA および PIM を設定した全体管理者専用アカウント

  Contoso 社は、グローバル管理者の役割を日常のユーザー アカウントに割り当てるのではなく、強力なパスワードを持つ 3 つの専用のグローバル管理者アカウントを作成しました。 アカウントは、Azure AD多要素認証 (MFA) と Azure Active Directory (Azure AD) 特権 ID 管理 (PIM) によって保護されます。 *PIM は、Microsoft 365 E5 でのみ使用可能です。*

  グローバル管理者アカウントでのサインインは、特定の管理タスクに対して行われます。 パスワードは、指定されたスタッフにのみ知られているので、Azure AD PIM で構成されている期間中にのみ使用できます。

  Contoso のセキュリティ管理者は、IT ワーカーのジョブ機能に適したアカウントに、より少ない管理者ロールを割り当てしました。

  詳細については、「[Microsoft 365 の管理者の役割](/office365/admin/add-users/about-admin-roles)」を参照してください。

- すべてのユーザー アカウントの MFA

  MFA は、サインイン プロセスに追加の保護層を追加します。 ユーザーは、パスワードを正しく入力した後、スマートフォンで電話、テキスト メッセージ、アプリ通知を確認する必要があります。 MFA を使用すると、アカウントADパスワードが侵害された場合でも、Azure ユーザー アカウントは承認されていないサインインから保護されます。

   - Microsoft 365 サブスクリプションの侵害から保護するには、すべてのグローバル管理者アカウントで MFA が必要です。
   - 組織内の信頼されている人の資格情報が漏えいし、攻撃者が悪意のある電子メールを送信するというフィッシング攻撃からの保護を目的として、Contoso 社ではマネージャーや経営幹部を含むすべてのユーザー アカウントで MFA を有効にしました。

- 条件付きアクセス ポリシーを使用したデバイスとアプリケーションへの安全なアクセス

  Contoso 社では、ID、デバイス、Exchange Online、および SharePoint に[条件付きアクセス ポリシー](../security/defender-365-security/microsoft-365-policies-configurations.md)を使用しています。ID の条件付きアクセス ポリシーには、リスクの高いユーザーに対するパスワード変更の要求や、クライアントに対する最新の認証をサポートしていないアプリの使用禁止が含まれます。デバイスのポリシーには、承認されたアプリを定義することや、準拠している PC とモバイル デバイスが必要になることが含まれます。Exchange Online の条件付きアクセス ポリシーには、ActiveSync クライアントのブロックと、Office 365 のメッセージ暗号化の設定が含まれます。SharePoint の条件付きアクセス ポリシーには、機密性の高い厳しく規制されたサイトに対する追加の保護が含まれます。

- Windows Hello for Business

  Contoso 社は [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification) を展開し、Windows 10 Enterprise を実行している PC とモバイル デバイスでの強力な 2 要素認証を通じて、最終的にパスワードの必要性を排除しました。

- Windows Defender Credential Guard

  管理特権を持つオペレーティング システムで実行されているターゲット攻撃とマルウェアをブロックするために、Contoso は DS グループ ポリシーを使用Windows Defender [Credential Guard](/windows/security/identity-protection/credential-guard/credential-guard) ADを有効にしました。

## <a name="threat-protection"></a>脅威保護

- Windows Defender ウイルス対策を使用したマルウェアからの保護

  Contoso 社では、Windows 10 Enterprise を実行する PC とデバイスのマルウェア対策およびマルウェア対策の管理に [Windows Defender ウイルス対策](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)を使用しています。

- Microsoft Defender を使用してメール フローとメールボックス監査ログをセキュリティで保護Office 365 

  Contoso 社は Exchange Online Protection と [Defender for Office 365](/office365/securitycompliance/office-365-atp) を使用して、電子メールを介して送信される未知のマルウェア、ウイルス、悪意のある URL から保護しています。

  Contoso では、メールボックス監査ログを有効にし、ユーザー のメールボックスへのログイン、メッセージの送信、メールボックス所有者、委任されたユーザー、または管理者によって実行されるその他のアクティビティを識別しました。

- Office 365 脅威の調査および対応を使用した攻撃の監視と防止

  Contoso は [、Office 365](/office365/securitycompliance/office-365-ti) の脅威調査と対応を使用して、攻撃の特定と対処を容易にし、将来の攻撃を防止することでユーザーを保護します。

- Advanced Threat Analytics を使用した高度な攻撃からの保護

  Contoso 社では、[Advanced Threat Analytics (ATA)](/advanced-threat-analytics/what-is-ata) を使用して高度な標的型の攻撃から自社を保護しています。ATA は自動的に、正常および異常なエンティティ (ユーザー、デバイス、およびリソース) の動作を分析、学習、識別します。

## <a name="information-protection"></a>情報保護

- Azure Information Protection ラベルを使用した機密性の高い厳しく規制されたデジタル資産の保護

  Contoso 社は、3 つのレベルのデータ保護を決定し、ユーザーがデジタル資産に適用する [Microsoft 365](../compliance/sensitivity-labels.md) の感度ラベルを展開しました。 企業秘密とその他の知的財産のために、Contoso は高度に規制されたデータに対して秘密度サブラベルを使用します。 このプロセスは、コンテンツを暗号化し、特定のユーザー アカウントとグループへのアクセスを制限します。

- データ損失防止機能を使用したイントラネット データの漏洩防止

  Contoso は [、ユーザー](../compliance/data-loss-prevention-policies.md) が誤ってまたは意図的に機密データを共有しないように、Exchange Online、SharePoint、OneDrive for Business のデータ損失防止ポリシーを構成しました。

- デバイスのデータ漏洩を防止する Windows 情報保護

  Contoso 社は [、Windows Information Protection (WIP)](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) を使用して、インターネット ベースのアプリやサービス、エンタープライズ アプリ、および従業員が仕事に持ち込む企業所有のデバイスおよび個人デバイス上のデータを通じてデータ漏洩から保護しています。

- Microsoft Cloud App Security を使用したクラウドの監視

  Contoso 社では [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) を使用して、自社のクラウド環境のマップ、使用状況を監視、セキュリティ イベントとインシデントの検出を行っています。 *Microsoft Cloud App Security は、Microsoft 365 E5 でのみ使用可能です。*

- Microsoft Intune を使用したデバイス管理

  Contoso 社では [Microsoft Intune](/intune/introduction-intune) を使用して、モバイル デバイスとその上で実行されるアプリへのアクセスを登録、管理、構成します。デバイスベースの条件付きアクセス ポリシーには、承認されたアプリと、準拠している PC とモバイル デバイスも必要です。

## <a name="security-management"></a>セキュリティ管理

- Azure Defender を使用した IT 向け中央セキュリティ ダッシュボード

  Contoso は [Azure Defender](https://azure.microsoft.com/services/security-center/) を使用して、セキュリティと脅威保護の統合ビューを提示し、ワークロード全体でセキュリティ ポリシーを管理し、サイバー攻撃に対応します。

- Windows Defender セキュリティ センターを使用したユーザー向けの中心となるセキュリティ ダッシュボード

  Contoso 社は [、Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) 10 Enterprise を実行している PC とデバイスに Windows セキュリティ アプリを展開し、ユーザーがセキュリティの状態を一目で確認してアクションを実行できるようにします。