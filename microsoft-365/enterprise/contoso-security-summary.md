---
title: Contoso Corporation 向けの Microsoft 365 Enterprise の概要
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が Microsoft 365 Enterprise 全体でセキュリティ機能を使用している方法について説明します。
ms.openlocfilehash: 394120f811057258afe1bd29e60733e42bf5191a
ms.sourcegitcommit: 4acd6fc368f547eb7a25d04799cb1a77003b143d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37372718"
---
# <a name="summary-of-microsoft-365-enterprise-security-for-the-contoso-corporation"></a><span data-ttu-id="70e25-103">Contoso Corporation 向けの Microsoft 365 Enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="70e25-103">Summary of Microsoft 365 Enterprise security for the Contoso Corporation</span></span>

<span data-ttu-id="70e25-104">**概要:** Contoso 社が Microsoft 365 Enterprise 全体でセキュリティ機能を使用している方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="70e25-104">**Summary:** How Contoso is using the security features across Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="70e25-p101">IT セキュリティ部門による Microsoft 365 Enterprise の展開の承認を得るために、徹底的なセキュリティ レビューが実施されました。Contoso 社でのクラウドに対するセキュリティ要件を次に示します。</span><span class="sxs-lookup"><span data-stu-id="70e25-p101">To obtain the sign-off of the deployment of Microsoft 365 Enterprise by the IT security department, a thorough security review was conducted. Here are Contoso's security requirements for the cloud:</span></span>

- <span data-ttu-id="70e25-107">クラウド リソースにアクセスする従業員に対して、最も強力な認証方法を使用します</span><span class="sxs-lookup"><span data-stu-id="70e25-107">Use the strongest methods of authentication for employee access to cloud resources</span></span>
- <span data-ttu-id="70e25-108">必ず PC とモバイル デバイスを接続し、セキュリティで保護された方法でアプリケーションにアクセスします</span><span class="sxs-lookup"><span data-stu-id="70e25-108">Ensure that PCs and mobile devices connect and access applications in secure ways</span></span>
- <span data-ttu-id="70e25-109">PC と電子メールをマルウェアから保護します</span><span class="sxs-lookup"><span data-stu-id="70e25-109">PCs and email are protected from malware</span></span>
- <span data-ttu-id="70e25-110">クラウド ベースのデジタル資産のアクセス許可は、アクセス可能なユーザー、アクセスの対象、ユーザーが実行できること、最小限の特権アクセス用にデザインされていることを定義します</span><span class="sxs-lookup"><span data-stu-id="70e25-110">Permissions on cloud-based digital assets define who can access what and what they can do and are designed for least privilege access</span></span>
- <span data-ttu-id="70e25-111">機密性の高い、厳しく規制されたデジタル資産にはラベルが付けられ、暗号化され、安全な場所に保管されます</span><span class="sxs-lookup"><span data-stu-id="70e25-111">Sensitive and highly regulated digital assets are labeled, encrypted, and stored in secure locations</span></span>
- <span data-ttu-id="70e25-112">厳しく規制されたデジタル資産は、追加の暗号化とアクセス許可で保護されます</span><span class="sxs-lookup"><span data-stu-id="70e25-112">Highly regulated digital assets are protected with permissions</span></span>
- <span data-ttu-id="70e25-113">IT セキュリティの担当者は、中心となるダッシュボードから現在のセキュリティの状況を監視できます。迅速な対応とリスク軽減のために、セキュリティ イベントの通知を受け取ることができます</span><span class="sxs-lookup"><span data-stu-id="70e25-113">IT security can monitor security posture from central dashboards and get notified of security events for quick response and mitigation</span></span>

## <a name="contosos-path-to-microsoft-365-security-readiness"></a><span data-ttu-id="70e25-114">Contoso 社の Microsoft 365 準備完了までのプロセス</span><span class="sxs-lookup"><span data-stu-id="70e25-114">Contoso's path to Microsoft 365 security readiness</span></span>

<span data-ttu-id="70e25-115">Contoso 社は、Microsoft 365 Enterprise の展開用に自社のセキュリティを準備するために、次の手順を行いました。</span><span class="sxs-lookup"><span data-stu-id="70e25-115">Contoso used the following steps to ready their security for their deployment of Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="70e25-116">クラウドの管理者アカウントを制限する</span><span class="sxs-lookup"><span data-stu-id="70e25-116">Limited administrator accounts for the cloud</span></span>

   <span data-ttu-id="70e25-117">Contoso 社では、既存の Active Directory Domain Services (AD DS) 管理者アカウントの広範なレビューを行い、一連の専用クラウド管理者アカウントおよびグループを設定しました。</span><span class="sxs-lookup"><span data-stu-id="70e25-117">Contoso did an extensive review of the existing Active Directory Domain Services (AD DS) administrator accounts and set up a series of cloud administrator accounts and groups.</span></span>

2. <span data-ttu-id="70e25-118">データ分析を行い 3 つのレベルに分類する</span><span class="sxs-lookup"><span data-stu-id="70e25-118">Performed data classification analysis into three levels</span></span>

   <span data-ttu-id="70e25-119">Contoso 社は慎重なレビューを行い、3 つのレベルを決定しました。これらのレベルは、Contoso 社の最も重要なデータを保護するための Microsoft 365 Enterprise の機能の決定に使用されました。</span><span class="sxs-lookup"><span data-stu-id="70e25-119">Contoso performed a careful review and determined the three levels, which was used to determine the Microsoft 365 Enterprise features to protect Contoso's most valuable data.</span></span>

3. <span data-ttu-id="70e25-120">各データ レベルに応じてアクセス ポリシー、保持ポリシー、情報保護ポリシーを決定した</span><span class="sxs-lookup"><span data-stu-id="70e25-120">Determined access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="70e25-121">データ レベルに基づき、Contoso 社は詳細な要件を決定しました。これらの要件は、クラウドに移動する将来の IT ワークロードを制限するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="70e25-121">Based on the data levels, Contoso determined detailed requirements, which will be used to qualify future IT workloads being moved to the cloud.</span></span>

<span data-ttu-id="70e25-122">セキュリティのベスト プラクティスと Microsoft 365 Enterprise 展開の要件に基づき、Contoso 社のセキュリティ管理者と IT 部門は次のセクションに示すように、数多くのセキュリティ機能を展開しました。</span><span class="sxs-lookup"><span data-stu-id="70e25-122">In accordance with security best practices and Microsoft 365 Enterprise deployment requirements, Contoso's security administrators and IT department have deployed many security features and capabilities, as described in the following sections.</span></span>

## <a name="identity--access-management"></a><span data-ttu-id="70e25-123">ID およびアクセス管理</span><span class="sxs-lookup"><span data-stu-id="70e25-123">Identity & access management</span></span> 

- <span data-ttu-id="70e25-124">MFA および PIM を設定した全体管理者専用アカウント</span><span class="sxs-lookup"><span data-stu-id="70e25-124">Dedicated global administrator accounts with MFA and PIM</span></span>

  <span data-ttu-id="70e25-125">Contoso 社では、日常的に使うユーザー アカウントに全体管理者ロールを割り当てるのではなく、強力なパスワードを設定した全体管理者専用アカウントを 3 つ作成し、それらをAzure 多要素認証 (MFA) と Azure Active Directory (Azure AD) Privileged Identity Management (PIM) で保護しました。</span><span class="sxs-lookup"><span data-stu-id="70e25-125">Rather than assign the global admin role to everyday user accounts, Contoso created three, dedicated global administrator accounts with very strong passwords and protected them with multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM).</span></span> <span data-ttu-id="70e25-126">PIM は、Microsoft 365 Enterprise E5 でのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="70e25-126">PIM is only available with Microsoft 365 Enterprise E5.</span></span>

  <span data-ttu-id="70e25-127">全体管理者アカウントでサインインするのは特定の管理タスクを実行するときのみで、パスワードは指定されたスタッフにのみ知らされています。パスワードは Azure AD PIM で設定された時間内にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="70e25-127">Signing in with a global administrator account is only done for specific administrative tasks, the passwords are only known to designated staff, and can only be used within the time configured with Azure AD PIM.</span></span> 

  <span data-ttu-id="70e25-128">Contoso 社のセキュリティ管理者は、IT 担当者の職務と責任に従って、各アカウントに一部の管理者ロールを割り当てました。</span><span class="sxs-lookup"><span data-stu-id="70e25-128">Contoso's security administrators have assigned lesser admin roles to accounts that are appropriate to that IT person's job function and responsibility.</span></span>

  <span data-ttu-id="70e25-129">詳細については、「[Office 365 の管理者の役割](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70e25-129">For more information, see [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="70e25-130">すべてのユーザー アカウントの MFA</span><span class="sxs-lookup"><span data-stu-id="70e25-130">MFA for all user accounts</span></span>

  <span data-ttu-id="70e25-p103">MFA を使用すると、サインイン プロセスの保護の層が厚くなり、パスワードを正しく入力した後、ユーザーに対して、電話、テキスト メッセージ、スマートフォンのアプリ通知のいずれかを通して確認が求められます。MFA を使用すれば、アカウント パスワードが漏えいした場合であっても、Azure AD ユーザー アカウントは承認されていないサインイン イベントから保護されます。</span><span class="sxs-lookup"><span data-stu-id="70e25-p103">MFA adds an additional layer of protection to the sign-in process by requiring users to acknowledge a phone call, text message, or an app notification on their smart phone after correctly entering their password. With MFA, Azure AD user accounts are protected against unauthorized sign-in even if an account password is compromised.</span></span>

   - <span data-ttu-id="70e25-133">Contoso 社では、Microsoft 365 サブスクリプションが危害を受けるのを防ぐため、すべての全体管理者アカウントで MFA を有効にしました。</span><span class="sxs-lookup"><span data-stu-id="70e25-133">To protect against a compromise of the Microsoft 365 subscription, Contoso requires MFA on all global administrator accounts.</span></span>
   - <span data-ttu-id="70e25-134">組織内の信頼されている人の資格情報が漏えいし、攻撃者が悪意のある電子メールを送信するというフィッシング攻撃からの保護を目的として、Contoso 社ではマネージャーや経営幹部を含むすべてのユーザー アカウントで MFA を有効にしました。</span><span class="sxs-lookup"><span data-stu-id="70e25-134">To protect against phishing attacks, in which an attacker compromises the credentials of a trusted person in the organization and sends malicious emails, Contoso enabled MFA on all user accounts, including manager and executive staff.</span></span> 

- <span data-ttu-id="70e25-135">条件付きアクセス ポリシーを使用したデバイスとアプリケーションへの安全なアクセス</span><span class="sxs-lookup"><span data-stu-id="70e25-135">Safer device and application access with conditional access policies</span></span>

  <span data-ttu-id="70e25-p104">Contoso 社では、ID、デバイス、Exchange Online、および SharePoint に[条件付きアクセス ポリシー](microsoft-365-policies-configurations.md)を使用しています。ID の条件付きアクセス ポリシーには、リスクの高いユーザーに対するパスワード変更の要求や、クライアントに対する最新の認証をサポートしていないアプリの使用禁止が含まれます。デバイスのポリシーには、承認されたアプリを定義することや、準拠している PC とモバイル デバイスが必要になることが含まれます。Exchange Online の条件付きアクセス ポリシーには、ActiveSync クライアントのブロックと、Office 365 のメッセージ暗号化の設定が含まれます。SharePoint の条件付きアクセス ポリシーには、機密性の高い厳しく規制されたサイトに対する追加の保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="70e25-p104">Contoso is using [conditional access policies](microsoft-365-policies-configurations.md) for identity, devices, Exchange Online, and SharePoint Online. Identity conditional access policies include requiring password changes for high-risk users and blocking clients from using apps that don’t support modern authentication. Device conditional policies include the definition of approved apps and requiring compliant PCs and mobile devices. Exchange Online conditional access policies include blocking ActiveSync clients and setting up Office 365 message encryption. SharePoint Online conditional access policies include additional protection for sensitive and highly regulated sites.</span></span>

- <span data-ttu-id="70e25-141">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="70e25-141">Windows Hello for Business</span></span>

  <span data-ttu-id="70e25-142">Contoso 社では、Windows 10 Enterprise を実行している PC とモバイル デバイスで強力な 2 要素認証を使用するパスワードの必要性を最終的に解消するために、[Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) を導入済みで、必須になっています。</span><span class="sxs-lookup"><span data-stu-id="70e25-142">Contoso has deployed and requires [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) to eventually eliminate the need for passwords with strong two-factor authentication on PCs and mobile devices running Windows 10 Enterprise.</span></span>

- <span data-ttu-id="70e25-143">Windows Defender Credential Guard</span><span class="sxs-lookup"><span data-stu-id="70e25-143">Windows Defender Credential Guard</span></span>

  <span data-ttu-id="70e25-144">管理者特権を使用してオペレーティング システムで実行されている標的型の攻撃やマルウェアをブロックするために、Contoso 社では AD DS グループ ポリシーを通じて [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) を有効にしています。</span><span class="sxs-lookup"><span data-stu-id="70e25-144">To block targeted attacks and malware running in the operating system with administrative privileges, Contoso has enabled [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) through AD DS group policy.</span></span>

## <a name="threat-protection"></a><span data-ttu-id="70e25-145">脅威保護</span><span class="sxs-lookup"><span data-stu-id="70e25-145">Threat protection</span></span>

- <span data-ttu-id="70e25-146">Windows Defender ウイルス対策を使用したマルウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="70e25-146">Protection from malware with Windows Defender Antivirus</span></span>

  <span data-ttu-id="70e25-147">Contoso 社では、Windows 10 Enterprise を実行する PC とデバイスのマルウェア対策およびマルウェア対策の管理に [Windows Defender ウイルス対策](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)を使用しています。</span><span class="sxs-lookup"><span data-stu-id="70e25-147">Contoso is using [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) for malware protection and anti-malware management for PCs and devices running Windows 10 Enterprise.</span></span>

- <span data-ttu-id="70e25-148">Office 365 Advanced Threat Protection を使用した安全な電子メールのフローとメールボックス監査ログ</span><span class="sxs-lookup"><span data-stu-id="70e25-148">Secure email flow and mailbox audit logging with Office 365 Advanced Threat Protection</span></span> 

  <span data-ttu-id="70e25-149">Contoso 社では、電子メール経由で送信される不明なマルウェア、ウイルス、悪意のある URL からの保護を目的として、Exchange Online Protection と [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="70e25-149">Contoso is using Exchange Online Protection and [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) to protect against unknown malware, viruses, and malicious URLs transmitted through emails.</span></span> 

  <span data-ttu-id="70e25-150">Contoso 社では、メールボックス監査ログを有効にして、ユーザーのメールボックスにログインしてメッセージを送信したのはだれかや、メールボックス所有者、委任ユーザー、管理者が実行した他の操作を判別しています。</span><span class="sxs-lookup"><span data-stu-id="70e25-150">Contoso has also enabled mailbox audit logging to determine who has logged into user mailboxes, sent messages, and other activities performed by the mailbox owner, a delegated user, or an administrator.</span></span>

- <span data-ttu-id="70e25-151">Office 365 脅威の調査および対応を使用した攻撃の監視と防止</span><span class="sxs-lookup"><span data-stu-id="70e25-151">Attack monitoring and prevention with Office 365 threat investigation and response</span></span>

  <span data-ttu-id="70e25-152">Contoso 社では、[Office 365 脅威の調査および対応](https://docs.microsoft.com/office365/securitycompliance/office-365-ti)を使用して攻撃の特定と対処を容易にし、将来の攻撃を防ぐことで、Office 365 ユーザーを保護します。</span><span class="sxs-lookup"><span data-stu-id="70e25-152">Contoso uses [Office 365 threat investigation and response](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) to protect their Office 365 users by making it easy to identify and address attacks, and to prevent future attacks.</span></span>

- <span data-ttu-id="70e25-153">Advanced Threat Analytics を使用した高度な攻撃からの保護</span><span class="sxs-lookup"><span data-stu-id="70e25-153">Protection from sophisticated attacks with Advanced Threat Analytics</span></span>

  <span data-ttu-id="70e25-p105">Contoso 社では、[Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) を使用して高度な標的型の攻撃から自社を保護しています。ATA は自動的に、正常および異常なエンティティ (ユーザー、デバイス、およびリソース) の動作を分析、学習、識別します。</span><span class="sxs-lookup"><span data-stu-id="70e25-p105">Contoso is using [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) to protect itself from advanced targeted attacks.  ATA automatically analyzes, learns, and identifies normal and abnormal entity (user, devices, and resources) behavior.</span></span> 

## <a name="information-protection"></a><span data-ttu-id="70e25-156">情報保護</span><span class="sxs-lookup"><span data-stu-id="70e25-156">Information protection</span></span>

- <span data-ttu-id="70e25-157">Azure Information Protection ラベルを使用した機密性の高い厳しく規制されたデジタル資産の保護</span><span class="sxs-lookup"><span data-stu-id="70e25-157">Protect sensitive and highly regulated digital assets with Azure Information Protection labels</span></span>

  <span data-ttu-id="70e25-p106">Contoso 社では 3 レベルのデータ保護を決定し、ユーザーがデジタル資産に適用する [Office 365 機密度ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)を展開しました。企業秘密やその他の知的財産について、Contoso 社では、コンテンツを暗号化し特定のユーザー アカウントとグループへのアクセスを制限する厳しく規制されたデータに対して、機密度サブラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="70e25-p106">Contoso determined three levels of data protection and deployed [Azure Information Protection](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) labels that users apply to digital assets. For its trade secrets and other intellectual property, Contoso uses Azure Information Protection sub-labels in a scoped policy for highly regulated data that encrypts content and restricts access to specific security groups.</span></span>

- <span data-ttu-id="70e25-160">Office 365 データ損失防止機能を使用したイントラネット データの漏洩防止</span><span class="sxs-lookup"><span data-stu-id="70e25-160">Prevent intranet data leaks with Office 365 Data Loss Prevention</span></span>

  <span data-ttu-id="70e25-161">Contoso 社では、Exchange Online、SharePoint、および OneDrive for Business 用に[データ損失防止](https://docs.microsoft.com/ja-JP/microsoft-365/compliance/data-loss-prevention-policies)ポリシーを構成し、故意か偶然かを問わずユーザーが機密データを共有することがないようにしています。</span><span class="sxs-lookup"><span data-stu-id="70e25-161">Contoso has configured [Data Loss Prevention](https://docs.microsoft.com/ja-JP/microsoft-365/compliance/data-loss-prevention-policies) policies for Exchange Online, SharePoint Online, and OneDrive for Business to prevent users from accidentally or intentionally sharing sensitive data.</span></span>

- <span data-ttu-id="70e25-162">デバイスのデータ漏洩を防止する Windows 情報保護</span><span class="sxs-lookup"><span data-stu-id="70e25-162">Prevent device data leaks Windows Information Protection</span></span>

  <span data-ttu-id="70e25-163">Contoso 社では [Windows 情報保護 (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) を使用して、インターネットベースのアプリとサービス、企業が所有するデバイスと従業員が仕事に携帯するデバイス上のエンタープライズ アプリとデータからデータが漏洩しないよう保護しています。</span><span class="sxs-lookup"><span data-stu-id="70e25-163">Contoso is using [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) to protect against data leakage through Internet-based apps and services and enterprise apps and data on enterprise-owned devices and personal devices that employees bring to work.</span></span>

- <span data-ttu-id="70e25-164">Microsoft Cloud App Security を使用したクラウドの監視</span><span class="sxs-lookup"><span data-stu-id="70e25-164">Cloud monitoring with Microsoft Cloud App Security</span></span>

  <span data-ttu-id="70e25-165">Contoso 社では [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) を使用して、自社のクラウド環境のマップ、使用状況を監視、セキュリティ イベントとインシデントの検出を行っています。</span><span class="sxs-lookup"><span data-stu-id="70e25-165">Contoso is using [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) to map their cloud environment, monitor its usage, and detect security events and incidents.</span></span> <span data-ttu-id="70e25-166">Microsoft Cloud App Security は、Microsoft 365 Enterprise E5 でのみ利用可能です。</span><span class="sxs-lookup"><span data-stu-id="70e25-166">Microsoft Cloud App Security is only available with Microsoft 365 Enterprise E5.</span></span>

- <span data-ttu-id="70e25-167">Microsoft Intune を使用したデバイス管理</span><span class="sxs-lookup"><span data-stu-id="70e25-167">Device management with Microsoft Intune</span></span>

  <span data-ttu-id="70e25-p108">Contoso 社では [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) を使用して、モバイル デバイスとその上で実行されるアプリへのアクセスを登録、管理、構成します。デバイスベースの条件付きアクセス ポリシーには、承認されたアプリと、準拠している PC とモバイル デバイスも必要です。</span><span class="sxs-lookup"><span data-stu-id="70e25-p108">As part of the Enterprise Management + Security (EMS) suite, Contoso uses [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) to enroll, manage, and configure access to mobile devices and the apps that run on them. Device-based conditional access policies also require approved apps and compliant PCs and mobile devices.</span></span>

## <a name="security-management"></a><span data-ttu-id="70e25-170">セキュリティ管理</span><span class="sxs-lookup"><span data-stu-id="70e25-170">Security management</span></span>

- <span data-ttu-id="70e25-171">Azure Security Center を使用した中心となる IT 用のセキュリティ ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="70e25-171">Central security dashboard for IT with Azure Security Center</span></span>

  <span data-ttu-id="70e25-172">Contoso 社では [Azure Security Center](https://azure.microsoft.com/services/security-center/) を使用して、セキュリティと脅威の保護を一元的に把握し、ワークロード全体でセキュリティ ポリシーを管理して、サイバー攻撃に対処しています。</span><span class="sxs-lookup"><span data-stu-id="70e25-172">Contoso uses the [Azure Security Center](https://azure.microsoft.com/services/security-center/) for a unified view of security and threat protection, to manage security policies across its workloads, and to respond to cyberattacks.</span></span>

- <span data-ttu-id="70e25-173">Windows Defender セキュリティ センターを使用したユーザー向けの中心となるセキュリティ ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="70e25-173">Central security dashboard for users with Windows Defender Security Center</span></span>

  <span data-ttu-id="70e25-174">Contoso 社では [Windows セキュリティ アプリ](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)を、Windows 10 Enterprise を実行する自社の PC およびデバイスに展開しました。これにより、ユーザーはセキュリティの状況を一目で把握し、対応策を講じることができます。</span><span class="sxs-lookup"><span data-stu-id="70e25-174">Contoso has deployed the [Windows Defender Security Center app](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) to its PCs and devices running Windows 10 Enterprise so that users can see their security posture at a glance and take action.</span></span>


## <a name="next-step"></a><span data-ttu-id="70e25-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="70e25-175">Next step</span></span>

<span data-ttu-id="70e25-176">Cotoso 社が社内の研究チーム間で共同作業を行えるようにするために、厳しく規制されたデータに対応した SharePoint サイトを作成した方法について[学習](contoso-sharepoint-online-site-for-highly-confidential-assets.md)します。</span><span class="sxs-lookup"><span data-stu-id="70e25-176">[Learn](contoso-sharepoint-online-site-for-highly-confidential-assets.md) how Contoso created a SharePoint Online site for highly regulated data to enable collaboration among its research teams.</span></span>

