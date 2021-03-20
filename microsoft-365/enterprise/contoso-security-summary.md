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
ms.openlocfilehash: 31baf61011fb67fbe11394718086d73afa2bc680
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907664"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a><span data-ttu-id="9b67c-103">Contoso Corporation のエンタープライズ セキュリティ向け Microsoft 365 の概要</span><span class="sxs-lookup"><span data-stu-id="9b67c-103">Summary of Microsoft 365 for enterprise security for the Contoso Corporation</span></span>

<span data-ttu-id="9b67c-104">Microsoft 365 for enterprise を展開する承認を得るに当たって、Contoso IT セキュリティ部門は徹底的なセキュリティ レビューを実施しました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-104">To get approval to deploy Microsoft 365 for enterprise, the Contoso IT security department conducted a thorough security review.</span></span> <span data-ttu-id="9b67c-105">クラウドの次のセキュリティ要件を特定しました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-105">They identified the following security requirements for the cloud:</span></span>

- <span data-ttu-id="9b67c-106">従業員がクラウド リソースにアクセスするには、最も強力な認証方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b67c-106">Use the strongest methods of authentication for employee access to cloud resources.</span></span>
- <span data-ttu-id="9b67c-107">PC とモバイル デバイスが安全な方法でアプリケーションに接続してアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b67c-107">Ensure that PCs and mobile devices connect and access applications in secure ways.</span></span>
- <span data-ttu-id="9b67c-108">PC と電子メールをマルウェアから保護します。</span><span class="sxs-lookup"><span data-stu-id="9b67c-108">Protect PCs and email from malware.</span></span>
- <span data-ttu-id="9b67c-109">クラウドベースのデジタル資産に対するアクセス許可は、誰が何にアクセスできるのか、何を実行できるのかを定義し、最小特権アクセス用に設計されています。</span><span class="sxs-lookup"><span data-stu-id="9b67c-109">Permissions on cloud-based digital assets define who can access what and what they can do, and are designed for least-privilege access</span></span>
- <span data-ttu-id="9b67c-110">機密性の高い高度に規制されたデジタル資産は、ラベル付けされ、暗号化され、安全な場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="9b67c-110">Sensitive and highly regulated digital assets are labeled, encrypted, and stored in secure locations.</span></span>
- <span data-ttu-id="9b67c-111">高度に規制されたデジタル資産は、追加の暗号化とアクセス許可で保護されます。</span><span class="sxs-lookup"><span data-stu-id="9b67c-111">Highly regulated digital assets are protected with additional encryption and permissions.</span></span>
- <span data-ttu-id="9b67c-112">IT セキュリティ スタッフは、中央ダッシュボードから現在のセキュリティ態勢を監視し、迅速な対応と軽減のためにセキュリティ イベントの通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9b67c-112">IT security staff can monitor the current security posture from central dashboards and get notified of security events for quick response and mitigation.</span></span>

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a><span data-ttu-id="9b67c-113">Microsoft 365 セキュリティ準備への Contoso パス</span><span class="sxs-lookup"><span data-stu-id="9b67c-113">The Contoso path to Microsoft 365 security readiness</span></span>

<span data-ttu-id="9b67c-114">Contoso 社は、エンタープライズ向け Microsoft 365 の展開に向けてセキュリティを準備するために、次の手順に従いました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-114">Contoso followed these steps to prepare their security for their deployment of Microsoft 365 for enterprise:</span></span>

1. <span data-ttu-id="9b67c-115">クラウドの管理者アカウントを制限する</span><span class="sxs-lookup"><span data-stu-id="9b67c-115">Limit administrator accounts for the cloud</span></span>

   <span data-ttu-id="9b67c-116">Contoso 社は、既存の Active Directory ドメイン サービス (AD DS) 管理者アカウントの詳細なレビューを行い、一連の専用クラウド管理者アカウントとグループを設定しました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-116">Contoso did an extensive review of its existing Active Directory Domain Services (AD DS) administrator accounts and set up series of dedicated cloud administrator accounts and groups.</span></span>

2. <span data-ttu-id="9b67c-117">データを 3 つのセキュリティ レベルに分類する</span><span class="sxs-lookup"><span data-stu-id="9b67c-117">Classify data into three security levels</span></span>

   <span data-ttu-id="9b67c-118">Contoso 社は、最も価値の高いデータを保護するために Microsoft 365 のエンタープライズ機能を特定するために使用された 3 つのレベルを慎重に検討し、決定しました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-118">Contoso did a careful review and determined the three levels, which were used to identify the Microsoft 365 for enterprise features to protect the most valuable data.</span></span>

3. <span data-ttu-id="9b67c-119">各データ レベルについてアクセス、保持、情報保護ポリシーを決定する</span><span class="sxs-lookup"><span data-stu-id="9b67c-119">Determine access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="9b67c-120">データ レベルに基づいて、Contoso はクラウドに移動される将来の IT ワークロードを修飾する詳細な要件を決定しました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-120">Based on the data levels, Contoso determined detailed requirements to qualify future IT workloads that are moved to the cloud.</span></span>

<span data-ttu-id="9b67c-121">エンタープライズ展開要件に関するセキュリティのベスト プラクティスと Microsoft 365 に従って、Contoso のセキュリティ管理者とその IT 部門は、次のセクションで説明するように、多くのセキュリティ機能と機能を展開しました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-121">To follow security best practices and Microsoft 365 for enterprise deployment requirements, Contoso security administrators and its IT department deployed many security features and capabilities, as described in the following sections.</span></span>

## <a name="identity-and-access-management"></a><span data-ttu-id="9b67c-122">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="9b67c-122">Identity and access management</span></span> 

- <span data-ttu-id="9b67c-123">MFA および PIM を設定した全体管理者専用アカウント</span><span class="sxs-lookup"><span data-stu-id="9b67c-123">Dedicated global administrator accounts with MFA and PIM</span></span>

  <span data-ttu-id="9b67c-124">Contoso 社は、グローバル管理者の役割を日常のユーザー アカウントに割り当てるのではなく、強力なパスワードを持つ 3 つの専用のグローバル管理者アカウントを作成しました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-124">Rather than assign the global admin role to everyday user accounts, Contoso created three dedicated global administrator accounts with strong passwords.</span></span> <span data-ttu-id="9b67c-125">アカウントは、Azure AD多要素認証 (MFA) と Azure Active Directory (Azure AD) 特権 ID 管理 (PIM) によって保護されます。</span><span class="sxs-lookup"><span data-stu-id="9b67c-125">The accounts are protected by Azure AD Multi-Factor Authentication (MFA) and Azure Active Directory (Azure AD) Privileged Identity Management (PIM).</span></span> <span data-ttu-id="9b67c-126">*PIM は、Microsoft 365 E5 でのみ使用可能です。*</span><span class="sxs-lookup"><span data-stu-id="9b67c-126">*PIM is only available with Microsoft 365 E5.*</span></span>

  <span data-ttu-id="9b67c-127">グローバル管理者アカウントでのサインインは、特定の管理タスクに対して行われます。</span><span class="sxs-lookup"><span data-stu-id="9b67c-127">Signing in with a global administrator account is only done for specific administrative tasks.</span></span> <span data-ttu-id="9b67c-128">パスワードは、指定されたスタッフにのみ知られているので、Azure AD PIM で構成されている期間中にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b67c-128">The passwords are only known to designated staff and can only be used within a time period that's configured in Azure AD PIM.</span></span>

  <span data-ttu-id="9b67c-129">Contoso のセキュリティ管理者は、IT ワーカーのジョブ機能に適したアカウントに、より少ない管理者ロールを割り当てしました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-129">Contoso security administrators assigned lesser admin roles to accounts that are appropriate to that IT worker's job function.</span></span>

  <span data-ttu-id="9b67c-130">詳細については、「[Microsoft 365 の管理者の役割](/office365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b67c-130">For more information, see [About Microsoft 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="9b67c-131">すべてのユーザー アカウントの MFA</span><span class="sxs-lookup"><span data-stu-id="9b67c-131">MFA for all user accounts</span></span>

  <span data-ttu-id="9b67c-132">MFA は、サインイン プロセスに追加の保護層を追加します。</span><span class="sxs-lookup"><span data-stu-id="9b67c-132">MFA adds an additional layer of protection to the sign-in process.</span></span> <span data-ttu-id="9b67c-133">ユーザーは、パスワードを正しく入力した後、スマートフォンで電話、テキスト メッセージ、アプリ通知を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b67c-133">It requires users to acknowledge a phone call, text message, or app notification on their smart phone after correctly entering their password.</span></span> <span data-ttu-id="9b67c-134">MFA を使用すると、アカウントADパスワードが侵害された場合でも、Azure ユーザー アカウントは承認されていないサインインから保護されます。</span><span class="sxs-lookup"><span data-stu-id="9b67c-134">With MFA, Azure AD user accounts are protected against unauthorized sign-in, even if an account password is compromised.</span></span>

   - <span data-ttu-id="9b67c-135">Microsoft 365 サブスクリプションの侵害から保護するには、すべてのグローバル管理者アカウントで MFA が必要です。</span><span class="sxs-lookup"><span data-stu-id="9b67c-135">To protect against compromise of the Microsoft 365 subscription, Contoso requires MFA on all global administrator accounts.</span></span>
   - <span data-ttu-id="9b67c-136">組織内の信頼されている人の資格情報が漏えいし、攻撃者が悪意のある電子メールを送信するというフィッシング攻撃からの保護を目的として、Contoso 社ではマネージャーや経営幹部を含むすべてのユーザー アカウントで MFA を有効にしました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-136">To protect against phishing attacks, in which an attacker compromises the credentials of a trusted person in the organization and sends malicious emails, Contoso enabled MFA on all user accounts, including managers and executives.</span></span>

- <span data-ttu-id="9b67c-137">条件付きアクセス ポリシーを使用したデバイスとアプリケーションへの安全なアクセス</span><span class="sxs-lookup"><span data-stu-id="9b67c-137">Safer device and application access with Conditional Access policies</span></span>

  <span data-ttu-id="9b67c-p105">Contoso 社では、ID、デバイス、Exchange Online、および SharePoint に[条件付きアクセス ポリシー](../security/office-365-security/microsoft-365-policies-configurations.md)を使用しています。ID の条件付きアクセス ポリシーには、リスクの高いユーザーに対するパスワード変更の要求や、クライアントに対する最新の認証をサポートしていないアプリの使用禁止が含まれます。デバイスのポリシーには、承認されたアプリを定義することや、準拠している PC とモバイル デバイスが必要になることが含まれます。Exchange Online の条件付きアクセス ポリシーには、ActiveSync クライアントのブロックと、Office 365 のメッセージ暗号化の設定が含まれます。SharePoint の条件付きアクセス ポリシーには、機密性の高い厳しく規制されたサイトに対する追加の保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b67c-p105">Contoso is using [Conditional Access policies](../security/office-365-security/microsoft-365-policies-configurations.md) for identity, devices, Exchange Online, and SharePoint. Identity Conditional Access policies include requiring password changes for high-risk users and blocking clients from using apps that don't support modern authentication. Device policies include the definition of approved apps and requiring compliant PCs and mobile devices. Exchange Online Conditional Access policies include blocking ActiveSync clients and setting up Office 365 message encryption. SharePoint Conditional Access policies include additional protection for sensitive and highly regulated sites.</span></span>

- <span data-ttu-id="9b67c-143">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="9b67c-143">Windows Hello for Business</span></span>

  <span data-ttu-id="9b67c-144">Contoso 社は [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification) を展開し、Windows 10 Enterprise を実行している PC とモバイル デバイスでの強力な 2 要素認証を通じて、最終的にパスワードの必要性を排除しました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-144">Contoso deployed [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification) to eventually eliminate the need for passwords through strong two-factor authentication on PCs and mobile devices running Windows 10 Enterprise.</span></span>

- <span data-ttu-id="9b67c-145">Windows Defender Credential Guard</span><span class="sxs-lookup"><span data-stu-id="9b67c-145">Windows Defender Credential Guard</span></span>

  <span data-ttu-id="9b67c-146">管理特権を持つオペレーティング システムで実行されているターゲット攻撃とマルウェアをブロックするために、Contoso は DS グループ ポリシーを使用Windows Defender [Credential Guard](/windows/security/identity-protection/credential-guard/credential-guard) ADを有効にしました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-146">To block targeted attacks and malware running in the operating system with administrative privileges, Contoso enabled [Windows Defender Credential Guard](/windows/security/identity-protection/credential-guard/credential-guard) through AD DS group policy.</span></span>

## <a name="threat-protection"></a><span data-ttu-id="9b67c-147">脅威保護</span><span class="sxs-lookup"><span data-stu-id="9b67c-147">Threat protection</span></span>

- <span data-ttu-id="9b67c-148">Windows Defender ウイルス対策を使用したマルウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="9b67c-148">Protection from malware with Windows Defender Antivirus</span></span>

  <span data-ttu-id="9b67c-149">Contoso 社では、Windows 10 Enterprise を実行する PC とデバイスのマルウェア対策およびマルウェア対策の管理に [Windows Defender ウイルス対策](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)を使用しています。</span><span class="sxs-lookup"><span data-stu-id="9b67c-149">Contoso is using [Windows Defender Antivirus](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) for malware protection and anti-malware management for PCs and devices running Windows 10 Enterprise.</span></span>

- <span data-ttu-id="9b67c-150">Microsoft Defender を使用してメール フローとメールボックス監査ログをセキュリティで保護Office 365</span><span class="sxs-lookup"><span data-stu-id="9b67c-150">Secure email flow and mailbox audit logging with Microsoft Defender for Office 365</span></span> 

  <span data-ttu-id="9b67c-151">Contoso 社は Exchange Online Protection と [Defender for Office 365](/office365/securitycompliance/office-365-atp) を使用して、電子メールを介して送信される未知のマルウェア、ウイルス、悪意のある URL から保護しています。</span><span class="sxs-lookup"><span data-stu-id="9b67c-151">Contoso is using Exchange Online Protection and [Defender for Office 365](/office365/securitycompliance/office-365-atp) to protect against unknown malware, viruses, and malicious URLs transmitted through emails.</span></span>

  <span data-ttu-id="9b67c-152">Contoso では、メールボックス監査ログを有効にし、ユーザー のメールボックスへのログイン、メッセージの送信、メールボックス所有者、委任されたユーザー、または管理者によって実行されるその他のアクティビティを識別しました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-152">Contoso also enabled mailbox audit logging to identify who logs in to user mailboxes, sends messages, and does other activities performed by the mailbox owner, a delegated user, or an administrator.</span></span>

- <span data-ttu-id="9b67c-153">Office 365 脅威の調査および対応を使用した攻撃の監視と防止</span><span class="sxs-lookup"><span data-stu-id="9b67c-153">Attack monitoring and prevention with Office 365 threat investigation and response</span></span>

  <span data-ttu-id="9b67c-154">Contoso は [、Office 365](/office365/securitycompliance/office-365-ti) の脅威調査と対応を使用して、攻撃の特定と対処を容易にし、将来の攻撃を防止することでユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="9b67c-154">Contoso uses [Office 365 threat investigation and response](/office365/securitycompliance/office-365-ti) to protect users by making it easy to identify and address attacks, and to prevent future attacks.</span></span>

- <span data-ttu-id="9b67c-155">Advanced Threat Analytics を使用した高度な攻撃からの保護</span><span class="sxs-lookup"><span data-stu-id="9b67c-155">Protection from sophisticated attacks with Advanced Threat Analytics</span></span>

  <span data-ttu-id="9b67c-p106">Contoso 社では、[Advanced Threat Analytics (ATA)](/advanced-threat-analytics/what-is-ata) を使用して高度な標的型の攻撃から自社を保護しています。ATA は自動的に、正常および異常なエンティティ (ユーザー、デバイス、およびリソース) の動作を分析、学習、識別します。</span><span class="sxs-lookup"><span data-stu-id="9b67c-p106">Contoso is using [Advanced Threat Analytics (ATA)](/advanced-threat-analytics/what-is-ata) to protect itself from advanced targeted attacks.  ATA automatically analyzes, learns, and identifies normal and abnormal entity (user, devices, and resources) behavior.</span></span>

## <a name="information-protection"></a><span data-ttu-id="9b67c-158">情報保護</span><span class="sxs-lookup"><span data-stu-id="9b67c-158">Information protection</span></span>

- <span data-ttu-id="9b67c-159">Azure Information Protection ラベルを使用した機密性の高い厳しく規制されたデジタル資産の保護</span><span class="sxs-lookup"><span data-stu-id="9b67c-159">Protect sensitive and highly regulated digital assets with Azure Information Protection labels</span></span>

  <span data-ttu-id="9b67c-160">Contoso 社は、3 つのレベルのデータ保護を決定し、ユーザーがデジタル資産に適用する [Microsoft 365](../compliance/sensitivity-labels.md) の感度ラベルを展開しました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-160">Contoso determined three levels of data protection and deployed [Microsoft 365 sensitivity labels](../compliance/sensitivity-labels.md) that users apply to digital assets.</span></span> <span data-ttu-id="9b67c-161">企業秘密とその他の知的財産のために、Contoso は高度に規制されたデータに対して秘密度サブラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b67c-161">For its trade secrets and other intellectual property, Contoso uses sensitivity sublabels for highly regulated data.</span></span> <span data-ttu-id="9b67c-162">このプロセスは、コンテンツを暗号化し、特定のユーザー アカウントとグループへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="9b67c-162">This process encrypts content and restricts access to specific user accounts and groups.</span></span>

- <span data-ttu-id="9b67c-163">データ損失防止機能を使用したイントラネット データの漏洩防止</span><span class="sxs-lookup"><span data-stu-id="9b67c-163">Prevent intranet data leaks with Data Loss Prevention</span></span>

  <span data-ttu-id="9b67c-164">Contoso は [、ユーザー](../compliance/data-loss-prevention-policies.md) が誤ってまたは意図的に機密データを共有しないように、Exchange Online、SharePoint、OneDrive for Business のデータ損失防止ポリシーを構成しました。</span><span class="sxs-lookup"><span data-stu-id="9b67c-164">Contoso configured [Data Loss Prevention](../compliance/data-loss-prevention-policies.md) policies for Exchange Online, SharePoint, and OneDrive for Business to prevent users from accidentally or intentionally sharing sensitive data.</span></span>

- <span data-ttu-id="9b67c-165">デバイスのデータ漏洩を防止する Windows 情報保護</span><span class="sxs-lookup"><span data-stu-id="9b67c-165">Prevent device data leaks Windows Information Protection</span></span>

  <span data-ttu-id="9b67c-166">Contoso 社は [、Windows Information Protection (WIP)](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) を使用して、インターネット ベースのアプリやサービス、エンタープライズ アプリ、および従業員が仕事に持ち込む企業所有のデバイスおよび個人デバイス上のデータを通じてデータ漏洩から保護しています。</span><span class="sxs-lookup"><span data-stu-id="9b67c-166">Contoso is using [Windows Information Protection (WIP)](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) to protect against data leakage through internet-based apps and services and enterprise apps and data on enterprise-owned devices and personal devices that employees bring to work.</span></span>

- <span data-ttu-id="9b67c-167">Microsoft Cloud App Security を使用したクラウドの監視</span><span class="sxs-lookup"><span data-stu-id="9b67c-167">Cloud monitoring with Microsoft Cloud App Security</span></span>

  <span data-ttu-id="9b67c-168">Contoso 社では [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) を使用して、自社のクラウド環境のマップ、使用状況を監視、セキュリティ イベントとインシデントの検出を行っています。</span><span class="sxs-lookup"><span data-stu-id="9b67c-168">Contoso is using [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) to map their cloud environment, monitor its usage, and detect security events and incidents.</span></span> <span data-ttu-id="9b67c-169">*Microsoft Cloud App Security は、Microsoft 365 E5 でのみ使用可能です。*</span><span class="sxs-lookup"><span data-stu-id="9b67c-169">*Microsoft Cloud App Security is only available with Microsoft 365 E5.*</span></span>

- <span data-ttu-id="9b67c-170">Microsoft Intune を使用したデバイス管理</span><span class="sxs-lookup"><span data-stu-id="9b67c-170">Device management with Microsoft Intune</span></span>

  <span data-ttu-id="9b67c-p109">Contoso 社では [Microsoft Intune](/intune/introduction-intune) を使用して、モバイル デバイスとその上で実行されるアプリへのアクセスを登録、管理、構成します。デバイスベースの条件付きアクセス ポリシーには、承認されたアプリと、準拠している PC とモバイル デバイスも必要です。</span><span class="sxs-lookup"><span data-stu-id="9b67c-p109">Contoso uses [Microsoft Intune](/intune/introduction-intune) to enroll, manage, and configure access to mobile devices and the apps that run on them. Device-based Conditional Access policies also require approved apps and compliant PCs and mobile devices.</span></span>

## <a name="security-management"></a><span data-ttu-id="9b67c-173">セキュリティ管理</span><span class="sxs-lookup"><span data-stu-id="9b67c-173">Security management</span></span>

- <span data-ttu-id="9b67c-174">Azure Defender を使用した IT 向け中央セキュリティ ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="9b67c-174">Central security dashboard for IT with Azure Defender</span></span>

  <span data-ttu-id="9b67c-175">Contoso は [Azure Defender](https://azure.microsoft.com/services/security-center/) を使用して、セキュリティと脅威保護の統合ビューを提示し、ワークロード全体でセキュリティ ポリシーを管理し、サイバー攻撃に対応します。</span><span class="sxs-lookup"><span data-stu-id="9b67c-175">Contoso uses the [Azure Defender](https://azure.microsoft.com/services/security-center/) to present a unified view of security and threat protection, to manage security policies across its workloads, and to respond to cyberattacks.</span></span>

- <span data-ttu-id="9b67c-176">Windows Defender セキュリティ センターを使用したユーザー向けの中心となるセキュリティ ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="9b67c-176">Central security dashboard for users with Windows Defender Security Center</span></span>

  <span data-ttu-id="9b67c-177">Contoso 社は [、Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) 10 Enterprise を実行している PC とデバイスに Windows セキュリティ アプリを展開し、ユーザーがセキュリティの状態を一目で確認してアクションを実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9b67c-177">Contoso deployed the [Windows Security app](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) to its PCs and devices running Windows 10 Enterprise so that users can see their security posture at a glance and take action.</span></span>