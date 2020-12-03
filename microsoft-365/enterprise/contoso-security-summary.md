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
ms.openlocfilehash: 5c951a973fbebeff92040f9411ad2c81788f920a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558396"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a><span data-ttu-id="d6a82-103">Contoso Corporation のエンタープライズセキュリティのための Microsoft 365 の概要</span><span class="sxs-lookup"><span data-stu-id="d6a82-103">Summary of Microsoft 365 for enterprise security for the Contoso Corporation</span></span>

<span data-ttu-id="d6a82-104">エンタープライズ向けに Microsoft 365 を展開するための承認を得るために、Contoso IT セキュリティ部門は完全なセキュリティレビューを実施していました。</span><span class="sxs-lookup"><span data-stu-id="d6a82-104">To get approval to deploy Microsoft 365 for enterprise, the Contoso IT security department conducted a thorough security review.</span></span> <span data-ttu-id="d6a82-105">クラウドのセキュリティ要件は次のように識別されました。</span><span class="sxs-lookup"><span data-stu-id="d6a82-105">They identified the following security requirements for the cloud:</span></span>

- <span data-ttu-id="d6a82-106">クラウドリソースへの従業員のアクセスには、最も強力な認証方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="d6a82-106">Use the strongest methods of authentication for employee access to cloud resources.</span></span>
- <span data-ttu-id="d6a82-107">Pc とモバイルデバイスが安全な方法で接続し、アプリケーションにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="d6a82-107">Ensure that PCs and mobile devices connect and access applications in secure ways.</span></span>
- <span data-ttu-id="d6a82-108">マルウェアから Pc とメールを保護します。</span><span class="sxs-lookup"><span data-stu-id="d6a82-108">Protect PCs and email from malware.</span></span>
- <span data-ttu-id="d6a82-109">クラウドベースのデジタルアセットに対するアクセス許可は、ユーザーが実行できる操作や、最小限の特権でアクセスできるように設計された機能にアクセスできるユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="d6a82-109">Permissions on cloud-based digital assets define who can access what and what they can do, and are designed for least-privilege access</span></span>
- <span data-ttu-id="d6a82-110">機密および高度に規制されたデジタル資産は、安全な場所にラベル付け、暗号化、保存を行います。</span><span class="sxs-lookup"><span data-stu-id="d6a82-110">Sensitive and highly regulated digital assets are labeled, encrypted, and stored in secure locations.</span></span>
- <span data-ttu-id="d6a82-111">高度な規制があるデジタルアセットは、追加の暗号化とアクセス許可で保護されています。</span><span class="sxs-lookup"><span data-stu-id="d6a82-111">Highly regulated digital assets are protected with additional encryption and permissions.</span></span>
- <span data-ttu-id="d6a82-112">IT セキュリティ担当者は、中央ダッシュボードから現在のセキュリティ姿勢を監視し、迅速な対応と軽減のためにセキュリティイベントの通知を受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="d6a82-112">IT security staff can monitor the current security posture from central dashboards and get notified of security events for quick response and mitigation.</span></span>

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a><span data-ttu-id="d6a82-113">Microsoft 365 のセキュリティの準備状況への Contoso のパス</span><span class="sxs-lookup"><span data-stu-id="d6a82-113">The Contoso path to Microsoft 365 security readiness</span></span>

<span data-ttu-id="d6a82-114">Contoso 社は、次の手順に従って、Microsoft 365 for enterprise の展開のセキュリティを準備します。</span><span class="sxs-lookup"><span data-stu-id="d6a82-114">Contoso followed these steps to prepare their security for their deployment of Microsoft 365 for enterprise:</span></span>

1. <span data-ttu-id="d6a82-115">クラウドの管理者アカウントを制限する</span><span class="sxs-lookup"><span data-stu-id="d6a82-115">Limit administrator accounts for the cloud</span></span>

   <span data-ttu-id="d6a82-116">Contoso 社は、既存の Active Directory ドメインサービス (AD DS) 管理者アカウントの広範なレビューを行い、一連の専用クラウド管理者アカウントおよびグループを設定しました。</span><span class="sxs-lookup"><span data-stu-id="d6a82-116">Contoso did an extensive review of its existing Active Directory Domain Services (AD DS) administrator accounts and set up series of dedicated cloud administrator accounts and groups.</span></span>

2. <span data-ttu-id="d6a82-117">3つのセキュリティレベルにデータを分類する</span><span class="sxs-lookup"><span data-stu-id="d6a82-117">Classify data into three security levels</span></span>

   <span data-ttu-id="d6a82-118">Contoso 社は慎重なレビューを行い、3つのレベルを決定しました。これは、最も重要なデータを保護するために、Microsoft 365 for enterprise 機能を識別するために使用されました。</span><span class="sxs-lookup"><span data-stu-id="d6a82-118">Contoso did a careful review and determined the three levels, which were used to identify the Microsoft 365 for enterprise features to protect the most valuable data.</span></span>

3. <span data-ttu-id="d6a82-119">各データ レベルについてアクセス、保持、情報保護ポリシーを決定する</span><span class="sxs-lookup"><span data-stu-id="d6a82-119">Determine access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="d6a82-120">データレベルに基づいて、Contoso 社はクラウドに移行される将来の IT ワークロードを見極めるための詳細な要件を決定しました。</span><span class="sxs-lookup"><span data-stu-id="d6a82-120">Based on the data levels, Contoso determined detailed requirements to qualify future IT workloads that are moved to the cloud.</span></span>

<span data-ttu-id="d6a82-121">エンタープライズ展開の要件についてセキュリティ上のベストプラクティスと Microsoft 365 を追跡するために、Contoso のセキュリティ管理者と IT 部門には、以下のセクションで説明するように、多くのセキュリティ機能が導入されています。</span><span class="sxs-lookup"><span data-stu-id="d6a82-121">To follow security best practices and Microsoft 365 for enterprise deployment requirements, Contoso security administrators and its IT department deployed many security features and capabilities, as described in the following sections.</span></span>

## <a name="identity-and-access-management"></a><span data-ttu-id="d6a82-122">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="d6a82-122">Identity and access management</span></span> 

- <span data-ttu-id="d6a82-123">MFA および PIM を設定した全体管理者専用アカウント</span><span class="sxs-lookup"><span data-stu-id="d6a82-123">Dedicated global administrator accounts with MFA and PIM</span></span>

  <span data-ttu-id="d6a82-124">Contoso 社は、グローバル管理者の役割を毎日のユーザーアカウントに割り当てる代わりに、強力なパスワードを持つ3つの専用のグローバル管理者アカウントを作成しました。</span><span class="sxs-lookup"><span data-stu-id="d6a82-124">Rather than assign the global admin role to everyday user accounts, Contoso created three dedicated global administrator accounts with strong passwords.</span></span> <span data-ttu-id="d6a82-125">アカウントは、Azure AD 多要素認証 (MFA) と Azure Active Directory (Azure AD) の特権 Id 管理 (PIM) によって保護されています。</span><span class="sxs-lookup"><span data-stu-id="d6a82-125">The accounts are protected by Azure AD Multi-Factor Authentication (MFA) and Azure Active Directory (Azure AD) Privileged Identity Management (PIM).</span></span> <span data-ttu-id="d6a82-126">*PIM は、Microsoft 365 E5 でのみ使用可能です。*</span><span class="sxs-lookup"><span data-stu-id="d6a82-126">*PIM is only available with Microsoft 365 E5.*</span></span>

  <span data-ttu-id="d6a82-127">全体管理者アカウントでのサインインは、特定の管理タスクに対してのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="d6a82-127">Signing in with a global administrator account is only done for specific administrative tasks.</span></span> <span data-ttu-id="d6a82-128">このパスワードは、指定されたスタッフのみが知っており、Azure AD PIM で構成された期間内にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d6a82-128">The passwords are only known to designated staff and can only be used within a time period that's configured in Azure AD PIM.</span></span>

  <span data-ttu-id="d6a82-129">Contoso のセキュリティ管理者は、その IT ワーカーのジョブ機能に適したアカウントに、管理者の役割の低い権限を割り当てています。</span><span class="sxs-lookup"><span data-stu-id="d6a82-129">Contoso security administrators assigned lesser admin roles to accounts that are appropriate to that IT worker's job function.</span></span>

  <span data-ttu-id="d6a82-130">詳細については、「[Microsoft 365 の管理者の役割](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6a82-130">For more information, see [About Microsoft 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="d6a82-131">すべてのユーザー アカウントの MFA</span><span class="sxs-lookup"><span data-stu-id="d6a82-131">MFA for all user accounts</span></span>

  <span data-ttu-id="d6a82-132">MFA は、サインインプロセスに追加の保護レイヤーを追加します。</span><span class="sxs-lookup"><span data-stu-id="d6a82-132">MFA adds an additional layer of protection to the sign-in process.</span></span> <span data-ttu-id="d6a82-133">ユーザーは、パスワードを正しく入力した後に、スマートフォンで電話、テキストメッセージ、アプリの通知について確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6a82-133">It requires users to acknowledge a phone call, text message, or app notification on their smart phone after correctly entering their password.</span></span> <span data-ttu-id="d6a82-134">MFA では、アカウントパスワードが侵害されても、Azure AD ユーザーアカウントは、不正なサインインから保護されます。</span><span class="sxs-lookup"><span data-stu-id="d6a82-134">With MFA, Azure AD user accounts are protected against unauthorized sign-in, even if an account password is compromised.</span></span>

   - <span data-ttu-id="d6a82-135">Microsoft 365 サブスクリプションが侵害されないように保護するために、Contoso にはすべてのグローバル管理者アカウントで MFA が必要です。</span><span class="sxs-lookup"><span data-stu-id="d6a82-135">To protect against compromise of the Microsoft 365 subscription, Contoso requires MFA on all global administrator accounts.</span></span>
   - <span data-ttu-id="d6a82-136">組織内の信頼されている人の資格情報が漏えいし、攻撃者が悪意のある電子メールを送信するというフィッシング攻撃からの保護を目的として、Contoso 社ではマネージャーや経営幹部を含むすべてのユーザー アカウントで MFA を有効にしました。</span><span class="sxs-lookup"><span data-stu-id="d6a82-136">To protect against phishing attacks, in which an attacker compromises the credentials of a trusted person in the organization and sends malicious emails, Contoso enabled MFA on all user accounts, including managers and executives.</span></span>

- <span data-ttu-id="d6a82-137">条件付きアクセス ポリシーを使用したデバイスとアプリケーションへの安全なアクセス</span><span class="sxs-lookup"><span data-stu-id="d6a82-137">Safer device and application access with Conditional Access policies</span></span>

  <span data-ttu-id="d6a82-p105">Contoso 社では、ID、デバイス、Exchange Online、および SharePoint に[条件付きアクセス ポリシー](../security/office-365-security/microsoft-365-policies-configurations.md)を使用しています。ID の条件付きアクセス ポリシーには、リスクの高いユーザーに対するパスワード変更の要求や、クライアントに対する最新の認証をサポートしていないアプリの使用禁止が含まれます。デバイスのポリシーには、承認されたアプリを定義することや、準拠している PC とモバイル デバイスが必要になることが含まれます。Exchange Online の条件付きアクセス ポリシーには、ActiveSync クライアントのブロックと、Office 365 のメッセージ暗号化の設定が含まれます。SharePoint の条件付きアクセス ポリシーには、機密性の高い厳しく規制されたサイトに対する追加の保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d6a82-p105">Contoso is using [Conditional Access policies](../security/office-365-security/microsoft-365-policies-configurations.md) for identity, devices, Exchange Online, and SharePoint. Identity Conditional Access policies include requiring password changes for high-risk users and blocking clients from using apps that don't support modern authentication. Device policies include the definition of approved apps and requiring compliant PCs and mobile devices. Exchange Online Conditional Access policies include blocking ActiveSync clients and setting up Office 365 message encryption. SharePoint Conditional Access policies include additional protection for sensitive and highly regulated sites.</span></span>

- <span data-ttu-id="d6a82-143">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="d6a82-143">Windows Hello for Business</span></span>

  <span data-ttu-id="d6a82-144">Contoso 社は、最終的に [Windows Hello For business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) を展開して、Windows 10 Enterprise を実行している pc とモバイルデバイスで強力な2要素認証を使用してパスワードを必要としなくなりました。</span><span class="sxs-lookup"><span data-stu-id="d6a82-144">Contoso deployed [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) to eventually eliminate the need for passwords through strong two-factor authentication on PCs and mobile devices running Windows 10 Enterprise.</span></span>

- <span data-ttu-id="d6a82-145">Windows Defender Credential Guard</span><span class="sxs-lookup"><span data-stu-id="d6a82-145">Windows Defender Credential Guard</span></span>

  <span data-ttu-id="d6a82-146">管理者特権を使用して、オペレーティングシステムで実行されている対象となる攻撃およびマルウェアをブロックするには、AD DS グループポリシーを経由する Contoso enabled [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d6a82-146">To block targeted attacks and malware running in the operating system with administrative privileges, Contoso enabled [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) through AD DS group policy.</span></span>

## <a name="threat-protection"></a><span data-ttu-id="d6a82-147">脅威保護</span><span class="sxs-lookup"><span data-stu-id="d6a82-147">Threat protection</span></span>

- <span data-ttu-id="d6a82-148">Windows Defender ウイルス対策を使用したマルウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="d6a82-148">Protection from malware with Windows Defender Antivirus</span></span>

  <span data-ttu-id="d6a82-149">Contoso 社では、Windows 10 Enterprise を実行する PC とデバイスのマルウェア対策およびマルウェア対策の管理に [Windows Defender ウイルス対策](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)を使用しています。</span><span class="sxs-lookup"><span data-stu-id="d6a82-149">Contoso is using [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) for malware protection and anti-malware management for PCs and devices running Windows 10 Enterprise.</span></span>

- <span data-ttu-id="d6a82-150">Microsoft Defender for Office 365 を使用した、セキュリティで保護されたメールフローとメールボックス監査ログ</span><span class="sxs-lookup"><span data-stu-id="d6a82-150">Secure email flow and mailbox audit logging with Microsoft Defender for Office 365</span></span> 

  <span data-ttu-id="d6a82-151">Contoso 社では、Exchange Online Protection と [Defender For Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) を使用して、電子メールで送信された不明なマルウェア、ウイルス、および悪意のある url から保護しています。</span><span class="sxs-lookup"><span data-stu-id="d6a82-151">Contoso is using Exchange Online Protection and [Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) to protect against unknown malware, viruses, and malicious URLs transmitted through emails.</span></span>

  <span data-ttu-id="d6a82-152">Contoso 社では、メールボックス監査ログを有効にして、ユーザーメールボックスにログインしたり、メッセージを送信したり、メールボックス所有者、委任されたユーザー、または管理者によって実行されたその他のアクティビティを識別したりしました。</span><span class="sxs-lookup"><span data-stu-id="d6a82-152">Contoso also enabled mailbox audit logging to identify who logs in to user mailboxes, sends messages, and does other activities performed by the mailbox owner, a delegated user, or an administrator.</span></span>

- <span data-ttu-id="d6a82-153">Office 365 脅威の調査および対応を使用した攻撃の監視と防止</span><span class="sxs-lookup"><span data-stu-id="d6a82-153">Attack monitoring and prevention with Office 365 threat investigation and response</span></span>

  <span data-ttu-id="d6a82-154">Contoso 社では、 [Office 365 の脅威調査と応答](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) を使用してユーザーを保護します。これにより、攻撃の特定と対処が容易になり、今後の攻撃を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="d6a82-154">Contoso uses [Office 365 threat investigation and response](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) to protect users by making it easy to identify and address attacks, and to prevent future attacks.</span></span>

- <span data-ttu-id="d6a82-155">Advanced Threat Analytics を使用した高度な攻撃からの保護</span><span class="sxs-lookup"><span data-stu-id="d6a82-155">Protection from sophisticated attacks with Advanced Threat Analytics</span></span>

  <span data-ttu-id="d6a82-p106">Contoso 社では、[Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) を使用して高度な標的型の攻撃から自社を保護しています。ATA は自動的に、正常および異常なエンティティ (ユーザー、デバイス、およびリソース) の動作を分析、学習、識別します。</span><span class="sxs-lookup"><span data-stu-id="d6a82-p106">Contoso is using [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) to protect itself from advanced targeted attacks.  ATA automatically analyzes, learns, and identifies normal and abnormal entity (user, devices, and resources) behavior.</span></span>

## <a name="information-protection"></a><span data-ttu-id="d6a82-158">情報保護</span><span class="sxs-lookup"><span data-stu-id="d6a82-158">Information protection</span></span>

- <span data-ttu-id="d6a82-159">Azure Information Protection ラベルを使用した機密性の高い厳しく規制されたデジタル資産の保護</span><span class="sxs-lookup"><span data-stu-id="d6a82-159">Protect sensitive and highly regulated digital assets with Azure Information Protection labels</span></span>

  <span data-ttu-id="d6a82-160">Contoso 社は、ユーザーがデジタル資産に適用する3つのレベルのデータ保護を決定し、 [Microsoft 365 の機密ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) を展開しました。</span><span class="sxs-lookup"><span data-stu-id="d6a82-160">Contoso determined three levels of data protection and deployed [Microsoft 365 sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) that users apply to digital assets.</span></span> <span data-ttu-id="d6a82-161">Contoso 社では、その取引機密とその他の知的財産に対して、高度な規制データに対して機密サブラベルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="d6a82-161">For its trade secrets and other intellectual property, Contoso uses sensitivity sublabels for highly regulated data.</span></span> <span data-ttu-id="d6a82-162">この処理によって、コンテンツが暗号化され、特定のユーザーアカウントおよびグループへのアクセスが制限されます。</span><span class="sxs-lookup"><span data-stu-id="d6a82-162">This process encrypts content and restricts access to specific user accounts and groups.</span></span>

- <span data-ttu-id="d6a82-163">データ損失防止機能を使用したイントラネット データの漏洩防止</span><span class="sxs-lookup"><span data-stu-id="d6a82-163">Prevent intranet data leaks with Data Loss Prevention</span></span>

  <span data-ttu-id="d6a82-164">Exchange Online、SharePoint、OneDrive for business の Contoso 社が構成した [データ損失防止](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) ポリシーにより、ユーザーが機密データを偶発的または故意に共有できないようにしています。</span><span class="sxs-lookup"><span data-stu-id="d6a82-164">Contoso configured [Data Loss Prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) policies for Exchange Online, SharePoint, and OneDrive for Business to prevent users from accidentally or intentionally sharing sensitive data.</span></span>

- <span data-ttu-id="d6a82-165">デバイスのデータ漏洩を防止する Windows 情報保護</span><span class="sxs-lookup"><span data-stu-id="d6a82-165">Prevent device data leaks Windows Information Protection</span></span>

  <span data-ttu-id="d6a82-166">Contoso 社では、 [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) を使用して、インターネットベースのアプリとサービス、および従業員が仕事に持参する個人用デバイス上のエンタープライズアプリとデータによるデータ漏洩から保護しています。</span><span class="sxs-lookup"><span data-stu-id="d6a82-166">Contoso is using [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) to protect against data leakage through internet-based apps and services and enterprise apps and data on enterprise-owned devices and personal devices that employees bring to work.</span></span>

- <span data-ttu-id="d6a82-167">Microsoft Cloud App Security を使用したクラウドの監視</span><span class="sxs-lookup"><span data-stu-id="d6a82-167">Cloud monitoring with Microsoft Cloud App Security</span></span>

  <span data-ttu-id="d6a82-168">Contoso 社では [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) を使用して、自社のクラウド環境のマップ、使用状況を監視、セキュリティ イベントとインシデントの検出を行っています。</span><span class="sxs-lookup"><span data-stu-id="d6a82-168">Contoso is using [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) to map their cloud environment, monitor its usage, and detect security events and incidents.</span></span> <span data-ttu-id="d6a82-169">*Microsoft Cloud App Security は、Microsoft 365 E5 でのみ使用可能です。*</span><span class="sxs-lookup"><span data-stu-id="d6a82-169">*Microsoft Cloud App Security is only available with Microsoft 365 E5.*</span></span>

- <span data-ttu-id="d6a82-170">Microsoft Intune を使用したデバイス管理</span><span class="sxs-lookup"><span data-stu-id="d6a82-170">Device management with Microsoft Intune</span></span>

  <span data-ttu-id="d6a82-p109">Contoso 社では [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) を使用して、モバイル デバイスとその上で実行されるアプリへのアクセスを登録、管理、構成します。デバイスベースの条件付きアクセス ポリシーには、承認されたアプリと、準拠している PC とモバイル デバイスも必要です。</span><span class="sxs-lookup"><span data-stu-id="d6a82-p109">Contoso uses [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) to enroll, manage, and configure access to mobile devices and the apps that run on them. Device-based Conditional Access policies also require approved apps and compliant PCs and mobile devices.</span></span>

## <a name="security-management"></a><span data-ttu-id="d6a82-173">セキュリティ管理</span><span class="sxs-lookup"><span data-stu-id="d6a82-173">Security management</span></span>

- <span data-ttu-id="d6a82-174">Azure Defender を使用した IT の中央セキュリティダッシュボード</span><span class="sxs-lookup"><span data-stu-id="d6a82-174">Central security dashboard for IT with Azure Defender</span></span>

  <span data-ttu-id="d6a82-175">Contoso 社では、 [Azure Defender](https://azure.microsoft.com/services/security-center/) を使用して、セキュリティと脅威保護の統一されたビューを提供し、そのワークロード全体にわたるセキュリティポリシーを管理し、cyberattacks に応答します。</span><span class="sxs-lookup"><span data-stu-id="d6a82-175">Contoso uses the [Azure Defender](https://azure.microsoft.com/services/security-center/) to present a unified view of security and threat protection, to manage security policies across its workloads, and to respond to cyberattacks.</span></span>

- <span data-ttu-id="d6a82-176">Windows Defender セキュリティ センターを使用したユーザー向けの中心となるセキュリティ ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="d6a82-176">Central security dashboard for users with Windows Defender Security Center</span></span>

  <span data-ttu-id="d6a82-177">Contoso 社は、windows 10 Enterprise を実行している Pc とデバイスに [Windows セキュリティアプリ](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) を展開し、ユーザーが自分のセキュリティ姿勢をひとめで確認し、アクションを実行できるようにしました。</span><span class="sxs-lookup"><span data-stu-id="d6a82-177">Contoso deployed the [Windows Security app](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) to its PCs and devices running Windows 10 Enterprise so that users can see their security posture at a glance and take action.</span></span>
