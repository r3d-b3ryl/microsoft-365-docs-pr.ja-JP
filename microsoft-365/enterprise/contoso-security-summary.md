---
title: Contoso Corporation のエンタープライズセキュリティのための Microsoft 365 の概要
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
description: Contoso 社では、Microsoft 365 for enterprise のセキュリティ機能を使用する方法について説明します。
ms.openlocfilehash: 8d62dba96ecf19f0dc31af2cf5a2d85257ca19d5
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847108"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Contoso Corporation のエンタープライズセキュリティのための Microsoft 365 の概要

エンタープライズ向けに Microsoft 365 を展開するための承認を得るために、Contoso IT セキュリティ部門は完全なセキュリティレビューを実施していました。 クラウドのセキュリティ要件は次のように識別されました。

- クラウドリソースへの従業員のアクセスには、最も強力な認証方法を使用します。
- Pc とモバイルデバイスが安全な方法で接続し、アプリケーションにアクセスできるようにします。
- マルウェアから Pc とメールを保護します。
- クラウドベースのデジタルアセットに対するアクセス許可は、ユーザーが実行できる操作や、最小限の特権でアクセスできるように設計された機能にアクセスできるユーザーを定義します。
- 機密および高度に規制されたデジタル資産は、安全な場所にラベル付け、暗号化、保存を行います。
- 高度な規制があるデジタルアセットは、追加の暗号化とアクセス許可で保護されています。
- IT セキュリティ担当者は、中央ダッシュボードから現在のセキュリティ姿勢を監視し、迅速な対応と軽減のためにセキュリティイベントの通知を受け取ることができます。

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>Microsoft 365 のセキュリティの準備状況への Contoso のパス

Contoso 社は、次の手順に従って、Microsoft 365 for enterprise の展開のセキュリティを準備します。

1. クラウドの管理者アカウントを制限する

   Contoso 社は、既存の Active Directory ドメインサービス (AD DS) 管理者アカウントの広範なレビューを行い、一連の専用クラウド管理者アカウントおよびグループを設定しました。

2. 3つのセキュリティレベルにデータを分類する

   Contoso 社は慎重なレビューを行い、3つのレベルを決定しました。これは、最も重要なデータを保護するために、Microsoft 365 for enterprise 機能を識別するために使用されました。

3. 各データ レベルについてアクセス、保持、情報保護ポリシーを決定する

   データレベルに基づいて、Contoso 社はクラウドに移行される将来の IT ワークロードを見極めるための詳細な要件を決定しました。

エンタープライズ展開の要件についてセキュリティ上のベストプラクティスと Microsoft 365 を追跡するために、Contoso のセキュリティ管理者と IT 部門には、以下のセクションで説明するように、多くのセキュリティ機能が導入されています。

## <a name="identity-and-access-management"></a>ID およびアクセス管理 

- MFA および PIM を設定した全体管理者専用アカウント

  Contoso 社は、グローバル管理者の役割を毎日のユーザーアカウントに割り当てる代わりに、強力なパスワードを持つ3つの専用のグローバル管理者アカウントを作成しました。 アカウントは、Azure 多要素認証 (MFA) と Azure Active Directory (Azure AD) の特権 Id 管理 (PIM) によって保護されています。 *PIM は、Microsoft 365 E5 でのみ使用可能です。*

  全体管理者アカウントでのサインインは、特定の管理タスクに対してのみ行われます。 このパスワードは、指定されたスタッフのみが知っており、Azure AD PIM で構成された期間内にのみ使用できます。

  Contoso のセキュリティ管理者は、その IT ワーカーのジョブ機能に適したアカウントに、管理者の役割の低い権限を割り当てています。

  詳細については、「[Microsoft 365 の管理者の役割](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)」を参照してください。

- すべてのユーザー アカウントの MFA

  MFA は、サインインプロセスに追加の保護レイヤーを追加します。 ユーザーは、パスワードを正しく入力した後に、スマートフォンで電話、テキストメッセージ、アプリの通知について確認する必要があります。 MFA では、アカウントパスワードが侵害されても、Azure AD ユーザーアカウントは、不正なサインインから保護されます。

   - Microsoft 365 サブスクリプションが侵害されないように保護するために、Contoso にはすべてのグローバル管理者アカウントで MFA が必要です。
   - 組織内の信頼されている人の資格情報が漏えいし、攻撃者が悪意のある電子メールを送信するというフィッシング攻撃からの保護を目的として、Contoso 社ではマネージャーや経営幹部を含むすべてのユーザー アカウントで MFA を有効にしました。

- 条件付きアクセス ポリシーを使用したデバイスとアプリケーションへの安全なアクセス

  Contoso 社では、ID、デバイス、Exchange Online、および SharePoint に[条件付きアクセス ポリシー](../security/office-365-security/microsoft-365-policies-configurations.md)を使用しています。ID の条件付きアクセス ポリシーには、リスクの高いユーザーに対するパスワード変更の要求や、クライアントに対する最新の認証をサポートしていないアプリの使用禁止が含まれます。デバイスのポリシーには、承認されたアプリを定義することや、準拠している PC とモバイル デバイスが必要になることが含まれます。Exchange Online の条件付きアクセス ポリシーには、ActiveSync クライアントのブロックと、Office 365 のメッセージ暗号化の設定が含まれます。SharePoint の条件付きアクセス ポリシーには、機密性の高い厳しく規制されたサイトに対する追加の保護が含まれます。

- Windows Hello for Business

  Contoso 社は、最終的に [Windows Hello For business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) を展開して、Windows 10 Enterprise を実行している pc とモバイルデバイスで強力な2要素認証を使用してパスワードを必要としなくなりました。

- Windows Defender Credential Guard

  管理者特権を使用して、オペレーティングシステムで実行されている対象となる攻撃およびマルウェアをブロックするには、AD DS グループポリシーを経由する Contoso enabled [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) を使用します。

## <a name="threat-protection"></a>脅威保護

- Windows Defender ウイルス対策を使用したマルウェアからの保護

  Contoso 社では、Windows 10 Enterprise を実行する PC とデバイスのマルウェア対策およびマルウェア対策の管理に [Windows Defender ウイルス対策](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)を使用しています。

- Microsoft Defender for Office 365 を使用した、セキュリティで保護されたメールフローとメールボックス監査ログ 

  Contoso 社では、Exchange Online Protection と [Defender For Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) を使用して、電子メールで送信された不明なマルウェア、ウイルス、および悪意のある url から保護しています。

  Contoso 社では、メールボックス監査ログを有効にして、ユーザーメールボックスにログインしたり、メッセージを送信したり、メールボックス所有者、委任されたユーザー、または管理者によって実行されたその他のアクティビティを識別したりしました。

- Office 365 脅威の調査および対応を使用した攻撃の監視と防止

  Contoso 社では、 [Office 365 の脅威調査と応答](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) を使用してユーザーを保護します。これにより、攻撃の特定と対処が容易になり、今後の攻撃を防ぐことができます。

- Advanced Threat Analytics を使用した高度な攻撃からの保護

  Contoso 社では、[Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) を使用して高度な標的型の攻撃から自社を保護しています。ATA は自動的に、正常および異常なエンティティ (ユーザー、デバイス、およびリソース) の動作を分析、学習、識別します。

## <a name="information-protection"></a>情報保護

- Azure Information Protection ラベルを使用した機密性の高い厳しく規制されたデジタル資産の保護

  Contoso 社は、ユーザーがデジタル資産に適用する3つのレベルのデータ保護を決定し、 [Microsoft 365 の機密ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) を展開しました。 Contoso 社では、その取引機密とその他の知的財産に対して、高度な規制データに対して機密サブラベルを使用しています。 この処理によって、コンテンツが暗号化され、特定のユーザーアカウントおよびグループへのアクセスが制限されます。

- データ損失防止機能を使用したイントラネット データの漏洩防止

  Exchange Online、SharePoint、OneDrive for business の Contoso 社が構成した [データ損失防止](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) ポリシーにより、ユーザーが機密データを偶発的または故意に共有できないようにしています。

- デバイスのデータ漏洩を防止する Windows 情報保護

  Contoso 社では、 [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) を使用して、インターネットベースのアプリとサービス、および従業員が仕事に持参する個人用デバイス上のエンタープライズアプリとデータによるデータ漏洩から保護しています。

- Microsoft Cloud App Security を使用したクラウドの監視

  Contoso 社では [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) を使用して、自社のクラウド環境のマップ、使用状況を監視、セキュリティ イベントとインシデントの検出を行っています。 *Microsoft Cloud App Security は、Microsoft 365 E5 でのみ使用可能です。*

- Microsoft Intune を使用したデバイス管理

  Contoso 社では [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) を使用して、モバイル デバイスとその上で実行されるアプリへのアクセスを登録、管理、構成します。デバイスベースの条件付きアクセス ポリシーには、承認されたアプリと、準拠している PC とモバイル デバイスも必要です。

## <a name="security-management"></a>セキュリティ管理

- Azure Defender による IT の中央セキュリティダッシュボード

  Contoso 社では、 [Azure Defender *](https://azure.microsoft.com/services/security-center/) を使用して、セキュリティと脅威保護の統一されたビューを提示し、そのワークロード全体にわたるセキュリティポリシーを管理し、cyberattacks に応答します。

- Windows Defender セキュリティ センターを使用したユーザー向けの中心となるセキュリティ ダッシュボード

  Contoso 社は、windows 10 Enterprise を実行している Pc とデバイスに [Windows セキュリティアプリ](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) を展開し、ユーザーが自分のセキュリティ姿勢をひとめで確認し、アクションを実行できるようにしました。
