---
title: フェーズ 5 - モバイル デバイスの管理
description: Microsoft 365 エンタープライズには、Microsoft Intune を使用してモバイル デバイスの管理が含まれています。要件と前提条件を確認、Intune は、Azure Active Directory リソースを使用して設定、macOS、iOS、Android、および Windows の登録、デバイス、アプリケーションを展開、構成プロファイルを作成、コンプライアンス ・ ポリシーを使用および携帯用の条件付きのアクセスを有効にします。Microsoft 365 エンタープライズ ・ デバイスの管理です。
keywords: Microsoft 365、Microsoft 365 エンタープライズでは、Microsoft 365 マニュアル、モバイル デバイスの管理、Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: 8d048ec6628cb8f7cb9c5e0d4c7960481bc69de1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869656"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a><span data-ttu-id="6c1ab-105">Microsoft 365 エンタープライズのフェーズ 5: モバイル デバイスの管理</span><span class="sxs-lookup"><span data-stu-id="6c1ab-105">Phase 5: Mobile device management for Microsoft 365 Enterprise</span></span>

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

<span data-ttu-id="6c1ab-106">*この機能は Microsoft 365 エンタープライズの E3、E5 のバージョンに適用されます。*</span><span class="sxs-lookup"><span data-stu-id="6c1ab-106">*This feature applies to the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="6c1ab-p102">Microsoft 365 エンタープライズには、デバイス、およびそれらのアプリケーションは、組織内での管理に役立つ機能が含まれています。Microsoft Intune を使用すると、iOS、Android、macOS、およびデータを含む、組織のリソースへのアクセスを保護するために Windows デバイスを管理できます。Intune は、Azure Active Directory (Azure AD) と統合 Microsoft 365 の次のビジネス シナリオを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p102">Microsoft 365 Enterprise includes features to help manage devices, and their apps, within your organization. Using Microsoft Intune, you can manage iOS, Android, macOS, and Windows devices to protect access to your organization's resources, including your data. Intune integrates with Azure Active Directory (Azure AD), and enables the following business scenarios for Microsoft 365:</span></span>

- <span data-ttu-id="6c1ab-110">組織内外でファイルを保管および共有して、組織の境界を越えてシームレスに作業を行います</span><span class="sxs-lookup"><span data-stu-id="6c1ab-110">Store and share files inside and outside your organization to work seamlessly across organizational boundaries</span></span>
- <span data-ttu-id="6c1ab-111">柔軟なワーク スタイルを維持しながら、いつでもどこでもデバイスを使って多くのことを安全に成し遂げることができます</span><span class="sxs-lookup"><span data-stu-id="6c1ab-111">Work securely from anywhere, anytime across your device to achieve more while maintaining a flexible workstyle</span></span>
- <span data-ttu-id="6c1ab-112">業界内で確証された世界標準のコンプライアンスに適合したコントロールと可視性により、安心感を提供します</span><span class="sxs-lookup"><span data-stu-id="6c1ab-112">Provide peace-of-mind with controls and visibility for industry-verified conformity with global standards in compliance</span></span>
- <span data-ttu-id="6c1ab-113">情報を保護して、データ損失のリスクを軽減します</span><span class="sxs-lookup"><span data-stu-id="6c1ab-113">Protect your information and reduce the risk of data loss</span></span>
- <span data-ttu-id="6c1ab-114">検出し、外部の脅威から保護します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-114">Detect and protect against external threats</span></span>
- <span data-ttu-id="6c1ab-115">監視、レポート、および組織のセキュリティを提供するのには迅速に対応する利用状況を分析</span><span class="sxs-lookup"><span data-stu-id="6c1ab-115">Monitor, report, and analyze activity to react promptly to provide organizational security</span></span>
- <span data-ttu-id="6c1ab-116">ユーザーと自分のアカウントを保護します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-116">Protect your users and their accounts</span></span>

<span data-ttu-id="6c1ab-117">詳細については、「[Microsoft 365 を使用したデジタル改革](http://transform.microsoft.com)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-117">For more information, see the [Digital transformation using Microsoft 365](http://transform.microsoft.com).</span></span> 

<span data-ttu-id="6c1ab-p103">このフェーズでは、作成し、セキュリティで保護され、データを保つためにポリシーを適用する Intune で、デバイスを登録します。Intune ドキュメントの全体のライブラリは、[利用可能なオンライン](https://docs.microsoft.com/intune)です。開始する前に[Intune 展開の計画、設計および実装ガイド](https://docs.microsoft.com/intune/planning-guide)を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p103">In this phase, you enroll your devices in Intune, and create and enforce policies to help keep your data secure and protected. The entire library of Intune documentation is [available online](https://docs.microsoft.com/intune). It's also good practice to review the [Intune deployment planning, design and implementation guide](https://docs.microsoft.com/intune/planning-guide) before you get started.</span></span>

## <a name="step-1-plan-for-your-scenario"></a><span data-ttu-id="6c1ab-121">シナリオでは、手順 1: 計画</span><span class="sxs-lookup"><span data-stu-id="6c1ab-121">Step 1: Plan for your scenario</span></span>

<span data-ttu-id="6c1ab-p104">モバイル デバイスを管理する主な理由の 1 つは、セキュリティで保護し、組織のリソースを保護するためにです。[Microsoft Intune を使用する一般的な方法](https://docs.microsoft.com/intune/common-scenarios)では、実際の例については、Office 365 の電子メールおよびデータのセキュリティ設定が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p104">One of the main reasons to manage mobile devices is to secure and protect your organization's resources. [Common ways to use Microsoft Intune](https://docs.microsoft.com/intune/common-scenarios) lists some real-world examples, including securing Office 365 email and data.</span></span>

<span data-ttu-id="6c1ab-p105">Intune では、[モバイル デバイス管理 (MDM) やモバイル アプリケーションの管理 (MAM)](https://docs.microsoft.com/intune/byod-technology-decisions)を使用して、組織へのアクセスを管理するためのオプションを示します。MDM は、ユーザーは Intune では、そのデバイスを「登録」とします。登録、管理対象デバイスであり、ポリシー、規則、および組織で使用される設定を受け取ることができます。などの具体的なアプリケーションのインストールのパスワード ポリシーを作成、VPN 接続をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p105">Intune gives you options to manage access to your organization using [Mobile Device Management (MDM) or Mobile Application Management (MAM)](https://docs.microsoft.com/intune/byod-technology-decisions). MDM is when users "enroll" their devices in Intune. Once enrolled, they are managed devices, and can receive any policies, rules, and settings used by your organization. For example, you can install specifics apps, create a password policy, install a VPN connection, and more.</span></span>

<span data-ttu-id="6c1ab-p106">自分個人のデバイスを持つユーザーすることがない、デバイスを登録または Intune のポリシーを管理します。組織のリソースとデータを保護する必要があります。このシナリオでは、MAM を使用して、アプリケーションを保護できます。たとえば、SharePoint をデバイスにアクセスするときに PIN を入力するユーザーを必要とする MAM ポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p106">Users with their own personal devices may not want to enroll their devices, or be managed by Intune and your policies. But, you still need to protect your organization's resources and data. In this scenario, you can protect your apps using MAM. For example, you can use a MAM policy that requires a user to enter a PIN when accessing SharePoint on the device.</span></span>

<span data-ttu-id="6c1ab-p107">どのようにしようとしている個人または組織が所有するデバイスを管理するかを決定します。使用によって、異なるデバイスを処理することができます。などの可能性がありますさまざまなプラン ユーザーに必要な人事 (HR) または販売のユーザーにします。[モバイル デバイス管理のユース ケース シナリオを識別](https://docs.microsoft.com/intune/planning-guide-scenarios)できますねと、さまざまなシナリオをいくつかのガイダンスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p107">You'll also determine how you're going to manage personal or organization-owned devices. You may want to treat devices differently, depending on their use. For example, you may want different plans for users in Human Resources (HR) or users in Sales. [Identify mobile device management use-case scenarios](https://docs.microsoft.com/intune/planning-guide-scenarios) can get you started, and includes some guidance on these different scenarios.</span></span>

## <a name="step-2-get-your-prerequisites"></a><span data-ttu-id="6c1ab-136">手順 2: 前提条件を取得します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-136">Step 2: Get your prerequisites</span></span>

<span data-ttu-id="6c1ab-p108">次に、前提条件がお客様の要件に基づいて、および前の手順で作成した独自のシナリオを取得します。[実装計画に](https://docs.microsoft.com/intune/planning-guide-onboarding)は、すべての要件を示します。Intune Microsoft 365 との必要な重要な項目を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p108">Next, get your prerequisites based on your requirements and your scenarios created in the previous step. [Implement your plan](https://docs.microsoft.com/intune/planning-guide-onboarding) lists all the requirements. Here are the significant items you need for Intune with Microsoft 365:</span></span>

- <span data-ttu-id="6c1ab-140">**Intune サブスクリプション**: Microsoft 365、 [Azure ポータル](https://portal.azure.com)の Microsoft Intune にアクセスすることに含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-140">**Intune subscription**: Included with Microsoft 365, and gives you access to Microsoft Intune in the [Azure portal](https://portal.azure.com)</span></span>
- <span data-ttu-id="6c1ab-141">**Office 365 サブスクリプション**: Microsoft 365 に含まれているし、メールを含む、Office アプリケーションの使用</span><span class="sxs-lookup"><span data-stu-id="6c1ab-141">**Office 365 subscription**: Included with Microsoft 365, and is used for Office apps, including email</span></span>
- <span data-ttu-id="6c1ab-p109">**Azure Active Directory (AD) プレミアム**: Microsoft 365 では、含まれており、ユーザーまたはセキュリティ グループを作成するために使用します。これらのグループを作成したら、Intune ポリシーを受信するデバイスのロックを解除するパスワードの長さを強制することなどです。作成するグループ[フェーズ 2: アイデンティティ](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p109">**Azure Active Directory (AD) premium**: Included with Microsoft 365, and is used to create user or security groups. These groups receive Intune policies that you create, such as forcing a password length to unlock a device. The groups you create in [Phase 2: Identity](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) can be used.</span></span>

<span data-ttu-id="6c1ab-p110">組織のニーズに応じて、いくつかの追加要件がある可能性があります。たとえば、iOS のデバイスを管理すること、Apple MDM のプッシュの証明書が必要があります。使用する場合、オンプレミスの Exchange、オンプレミスの Exchange コネクタを必要があります。これらの手順を表示するときにこれらの要件の概要です。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p110">There may be some additional requirements, depending on your organization's needs. For example, if you'll be managing iOS devices, you'll need an Apple MDM Push certificate. If you're using on-premises Exchange, then you'll need the on-premises Exchange connector. These additional requirements are outlined when you get to those steps.</span></span>

## <a name="step-3-set-up-intune"></a><span data-ttu-id="6c1ab-149">Intune セットアップの手順 3:</span><span class="sxs-lookup"><span data-stu-id="6c1ab-149">Step 3: Set up Intune</span></span>

<span data-ttu-id="6c1ab-p111">Intune では、Azure AD、ドメイン、ユーザー、グループなどの多くの機能を使用します。企業のニーズに合わせて新しいユーザーや新しいグループを作成することもできます。たとえば、 **iOS デバイス**、または**人事部のすべてのユーザー**と呼ばれるグループを作成できます。 単純または高度なルールに基づいてデバイス ・ グループまたはユーザーのいずれかを作成できる[動的なグループ](https://docs.microsoft.com/intune/groups-add)を利用します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p111">Intune uses many features in Azure AD, including your domain, your users, and your groups. You can also create new users and new groups to fit your company needs. For example, you can create a group called **iOS devices**, or **All HR users**.  Take advantage of [Dynamic Groups](https://docs.microsoft.com/intune/groups-add) that lets you build either user or device groups based around simple or advanced rules.</span></span>

<span data-ttu-id="6c1ab-154">この手順は、Intune を設定して、デバイスを管理するために準備に焦点を当てます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-154">This step focuses on setting up Intune, and getting it ready for you to manage your devices.</span></span>

1. <span data-ttu-id="6c1ab-p112">**[デバイスがサポートされているを確認](https://docs.microsoft.com/intune/supported-devices-browsers)** します。MacOS、iOS の確認、Intune によって Android、Galaxy では、Windows のデバイスがサポートされています。組織にはではサポートされていないデバイスが含まれている場合、ポリシーは、それらのデバイスに適用されません。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p112">**[Confirm your devices are supported](https://docs.microsoft.com/intune/supported-devices-browsers)**. Confirm your iOS, macOS, Android, Galaxy, and Windows devices are supported by Intune. If your organization includes devices that aren't supported, then the policies aren't applied to those devices.</span></span>

2. <span data-ttu-id="6c1ab-p113">**[ドメイン名をカスタマイズ](https://docs.microsoft.com/intune/custom-domain-name-configure)** します。既定では、ドメインの名前が**domain.onmicrosoft.com では、** 自動的には Azure AD のように。**onmicrosoft.com**は、組織に合わせてカスタマイズできます。カスタマイズすると、こともできます一般的なドメインの接続時に Intune とリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p113">**[Customize your domain name](https://docs.microsoft.com/intune/custom-domain-name-configure)**. By default, a domain named something like **your-domain.onmicrosoft.com** is automatically created in Azure AD. **onmicrosoft.com** can be customized for your organization. When you customize, it also gives users a familiar domain when connecting to Intune and using resources.</span></span>

3. <span data-ttu-id="6c1ab-p114">**[Intune にサインイン](https://docs.microsoft.com/intune/account-sign-up)** します。サインインするとき、組織に関する情報を入力する必要があります。Intune は、Microsoft 365 に含まれ、 [Office 365 管理ポータル](https://portal.office.com/)から直接開くことができます。Intune は、 [Azure ポータル](https://portal.azure.com)から直接開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p114">**[Sign in to Intune](https://docs.microsoft.com/intune/account-sign-up)**. When you sign in, you may be prompted to enter information about your organization. Intune is included with Microsoft 365, and can be opened directly from the [Office 365 Admin portal](https://portal.office.com/). You can also open Intune directly from the [Azure portal](https://portal.azure.com).</span></span>

4. <span data-ttu-id="6c1ab-p115">**[、モバイル デバイス管理の構成を選択](https://docs.microsoft.com/intune/mdm-authority-set)** します。初めて Intune を使用するデバイスの管理を有効にする必要があります。Intune は、クラウド専用サービスで、Intune およびシステム センター構成マネージャーでは、Office 365 でモバイル デバイス管理を使用すると、ハイブリッドとして使用できます。組織に最適な設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p115">**[Choose your mobile device management configuration](https://docs.microsoft.com/intune/mdm-authority-set)**. The first time you use Intune, you must enable device management. Intune can be used as a cloud-only service, a hybrid with Intune and System Center Configuration Manager, or using Mobile Device Management for Office 365. You can choose which setup works best for your organization.</span></span>

5. <span data-ttu-id="6c1ab-170">**[追加ユーザー](https://docs.microsoft.com/intune/users-add)** および**[グループを追加](https://docs.microsoft.com/intune/groups-add)** します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-170">**[Add users](https://docs.microsoft.com/intune/users-add)** and **[add groups](https://docs.microsoft.com/intune/groups-add)**.</span></span> 

   <span data-ttu-id="6c1ab-p116">手動でユーザーを追加したり、Intune でユーザーの同期に Azure の AD に接続できます。特定のユーザーに管理者の役割を与えることができます。ユーザーは、デバイスは、キオスク デバイスなどの"userless"のデバイスでない限り必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p116">You can manually add users, or connect to Azure AD to sync users with Intune. You can also give Admin roles to specific users. Users are required unless your devices are "userless" devices, such as kiosk devices.</span></span>

   <span data-ttu-id="6c1ab-p117">Azure AD グループは、デバイスと Intune でユーザーを管理する方法を簡略化に使用されます。グループを使用すると、さまざまなタスクを実行できます。たとえば、組織では、Android デバイス上の特定のアプリケーションを必要とするが。、Android のデバイス グループを作成し、このアプリケーションのポリシーをグループに配置できます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p117">Azure AD groups are used to simplify how you manage devices and users in Intune. Using groups, you can do many different tasks. For example, your organization wants to require a specific app on Android devices. You can create an Android devices group, and deploy a policy with this app to the group.</span></span>

    <span data-ttu-id="6c1ab-178">Intune では、ユーザーまたはグループで作成するを追加できます[フェーズ 2: アイデンティティ](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)</span><span class="sxs-lookup"><span data-stu-id="6c1ab-178">In Intune, you can add users or groups that you create in [Phase 2: Identity](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure)</span></span>

6. <span data-ttu-id="6c1ab-p118">**[ライセンスを割り当てます](https://docs.microsoft.com/intune/licenses-assign)**。Intune に登録するユーザーまたはデバイス、デバイスのライセンスが必要です。各ユーザーまたはデバイスの userless には、Intune Intune サービスにアクセスするのにはライセンスが必要です。これらのライセンスは、マイクロソフトの 365 に含まれているし、Intune に割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p118">**[Assign licenses](https://docs.microsoft.com/intune/licenses-assign)**. For users or devices to enroll in Intune, they need a license on the device. Each user or userless device requires an Intune license to access the Intune service. These licenses are included with Microsoft 365, and must be assigned in Intune.</span></span>

## <a name="step-4-enroll-devices"></a><span data-ttu-id="6c1ab-183">手順 4: デバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-183">Step 4: Enroll devices</span></span>

<span data-ttu-id="6c1ab-p119">デバイスを管理するためには、Intune にデバイスを登録する必要があります。管理者は、登録の制限およびユーザーとデバイスのポリシーを設定します。各デバイスのプラットフォーム (iOS、Android、macOS、および Windows) では、さまざまなオプションがあります。ユーザー自身を登録することができます。または、登録を自動化するには、ユーザーがデバイスを単にサインインするようにします。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p119">To manage devices, the devices must be enrolled in Intune. As an administrator, you’ll set up enrollment restrictions and policies for your users and devices. Each device platform (iOS, Android, macOS, and Windows) has a variety of options. You can have your users enroll themselves. Or, you can automate enrollment so users simply sign in to the device.</span></span>

<span data-ttu-id="6c1ab-p120">登録は Intune を使用する場合、重要なステップです。[登録デバイス](https://docs.microsoft.com/intune/device-enrollment)は、さまざまなデバイス用の手順を示します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p120">Enrollment is a key step when using Intune. [Enroll devices](https://docs.microsoft.com/intune/device-enrollment) lists the steps for the different devices.</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="6c1ab-192">テスト ラボ ガイド: iOS および Android デバイスの登録</span><span class="sxs-lookup"><span data-stu-id="6c1ab-192">Test Lab Guide: iOS and Android device enrollment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a><span data-ttu-id="6c1ab-193">手順 5: を追加し、アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-193">Step 5: Add and deploy apps</span></span>

<span data-ttu-id="6c1ab-194">モバイル デバイス上のアプリは、多くの場合最も簡単な方法のユーザーが企業リソースへのアクセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-194">Apps on mobile devices are often the quickest way users get access to your corporate resources.</span></span> 

<span data-ttu-id="6c1ab-p121">課題アプリケーションを使用する場合は個人用デバイス、デバイスの企業など、さまざまなデバイスがあります。組織のリソースとそのデータを保護する一方で、ユーザーが生産性を向上します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p121">There are challenges when using apps, as there are different devices, including personal devices and corporate devices. And, you want to protect your organization's resources and its data while also making sure users are productive.</span></span>

<span data-ttu-id="6c1ab-p122">Intune などのアプリケーションを管理できるアプリケーションを追加、別のユーザーまたはグループに割り当てる、およびその他の重要な詳細事項を確認します。などをインストールするには、アプリケーション、および複数のバージョンを確認するアプリケーションが失敗するかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p122">Intune can manage apps, including add apps, assign them to different users or groups, and review other key details. For example, you can see which apps fail to install, check the version of an app, and more.</span></span>

<span data-ttu-id="6c1ab-p123">ユーザーがモバイル デバイスを取得するとき組織の電子メールやドキュメントにアクセスする最初のタスクの 1 つです。Intune を使用すると、することができます[を作成し電子メールの設定を展開する](https://docs.microsoft.com/intune/email-settings-configure)デバイスに事前にインストールされている電子メール アプリケーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p123">When users get a mobile device, one of the first tasks is to access organizational email and documents. Using Intune, you can [create and deploy email settings](https://docs.microsoft.com/intune/email-settings-configure) using email apps that are pre-installed on the devices.</span></span> 

<span data-ttu-id="6c1ab-201">[追加アプリケーション](https://docs.microsoft.com/intune/app-management)の追加、展開、監視、構成、および、組織内のデバイスにアプリケーションを保護するための手順を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-201">[Add apps](https://docs.microsoft.com/intune/app-management) lists the steps to add, deploy, monitor, configure, and protect apps on devices within your org.</span></span>

|||
|:-------|:-----|
|![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="6c1ab-203">モバイル アプリケーション管理ポリシーのテスト ラボ ガイド:</span><span class="sxs-lookup"><span data-stu-id="6c1ab-203">Test Lab Guide: Mobile application management policies</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a><span data-ttu-id="6c1ab-204">手順 6: は、コンプライアンスと条件付きのアクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-204">Step 6: Turn on compliance and conditional access</span></span>

<span data-ttu-id="6c1ab-p124">、前の手順では、環境を設定し、Intune を有効にします。これで、コンプライアンスと条件付きのアクセスを使用していくつかのポリシーを作成する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p124">In the previous steps, you set up your environment, and enabled Intune. Now, you're ready to create some policies using compliance and conditional access.</span></span>

<span data-ttu-id="6c1ab-p125">コンプライアンスと条件付きのアクセスは、デバイスを管理するのには重要です。**[コンプライアンス ・ ポリシー](https://docs.microsoft.com/intune/device-compliance-get-started)** は、組織のリソースを保護するために作成されます。コンプライアンス ・ ポリシーを作成するときは、標準またはのデバイスである必要があります「ベースライン」を定義しています。など、許容可能な (またはできない) の脅威のレベルを選択して jailbroken デバイスをブロックする、パスワードの長さなどを必要とすることがことができます。準拠ではないので、ルールの目的はこれらのデバイスがない場合は、リソースへのアクセスをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p125">Compliance and conditional access are important to managing devices. **[Compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started)** are created to help protect your organization's resources. When you create a compliance policy, you're defining the standard or the "baseline" of what a device must have. For example, you can choose an acceptable (or unacceptable) threat level, block jailbroken devices, require a password length, and more. If these devices don't meet your rules, meaning they aren't compliant, then you can block access to your resources.</span></span>

<span data-ttu-id="6c1ab-p126">これは、「ブロック」**[条件付きのアクセス](https://docs.microsoft.com/intune/conditional-access)** を紹介します。デバイスは、非準拠と見なされます、電子メール、SharePoint、および詳細へのアクセスをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p126">This "blocking" introduces **[Conditional access](https://docs.microsoft.com/intune/conditional-access)**. If a device is considered not-compliant, then you can block access to email, SharePoint, and more.</span></span>

<span data-ttu-id="6c1ab-p127">[Azure ポータル](https://portal.azure.com)で Intune では、これらのポリシーを作成し、ユーザーおよびデバイスに適用することができます。ベスト プラクティスとして、小規模、および段階的なアプローチを使用します。たとえば、jailbroken デバイスをブロックする iOS のポリシーを作成します。パイロットまたはテストのグループに (と呼ばれる「割り当てる」Intune の) ポリシーを適用します。初期テストでは後に、、パイロット グループをより多くのユーザーを追加します。段階的なアプローチを使用するには、さまざまな種類のユーザーからのフィードバックを取得できます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p127">Intune in the [Azure portal](https://portal.azure.com) lets you create these policies, and apply them to your users and devices. As a best practice, start small, and use a staged approach. For example, create an iOS policy that blocks jailbroken devices. Apply (called "assign" in Intune) the policy to a pilot or test group. After initial testing, add more users to the pilot group. Using a staged approach, you can get feedback from a wide range of user types.</span></span>

<span data-ttu-id="6c1ab-220">[コンプライアンス ポリシーのデバイスを使い始める](https://docs.microsoft.com/intune/device-compliance-get-started)と[条件付きアクセスとは何ですか。](https://docs.microsoft.com/intune/conditional-access)を開始することができます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-220">[Get started with device compliance policies](https://docs.microsoft.com/intune/device-compliance-get-started) and [What's conditional access?](https://docs.microsoft.com/intune/conditional-access) can help you get started.</span></span>

## <a name="step-7-apply-features-and-settings"></a><span data-ttu-id="6c1ab-221">機能と設定を適用する手順 7。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-221">Step 7: Apply features and settings</span></span>

<span data-ttu-id="6c1ab-p128">これらの機能と設定は、Intune の「cool」の一部と見なされると非常に強力な。条件付きのアクセスを使用していくつかのコンプライアンス ・ ポリシーを適用して正常にしたら**デバイスのプロファイル**を作成します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p128">These features and settings are often considered the "cool" part of Intune, and are very powerful. Once you've successfully enforced some compliance policies using conditional access, you're ready to create **Device profiles**.</span></span>

<span data-ttu-id="6c1ab-p129">Intune [Azure ポータル](https://portal.azure.com)を使用して、macOS、iOS、Android、および Windows のデバイス プラットフォームに基づく別のプロファイルを作成できます。たとえば、次のようなことができます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p129">Intune in the [Azure portal](https://portal.azure.com) lets you create different profiles based on your device platform - iOS, macOS, Android, and Windows. For example, you can:</span></span>

- <span data-ttu-id="6c1ab-226">暗号化を含む、BitLocker のさまざまなオプションを有効にするのに 10 の Windows デバイス上のエンドポイントの保護を使用します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-226">Use Endpoint protection on Windows 10 devices to enable different BitLocker options, including encryption.</span></span>
- <span data-ttu-id="6c1ab-p130">IOS デバイスにインストールできる承認済みアプリケーションのリストを作成するのにアプリケーションの制限機能を使用します。または、禁止されているアプリケーションの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p130">Use the Restricted apps feature on iOS devices to create a list of approved apps that can be installed. Or, create a list of prohibited apps.</span></span>
- <span data-ttu-id="6c1ab-229">キオスクの設定を使用すると、キオスク モードで実行している Android のデバイスでどのアプリケーションを使用することができます」を選択します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-229">Use the Kiosk settings to choose which apps can be used on Android devices running in kiosk mode.</span></span>
- <span data-ttu-id="6c1ab-230">Wi-fi 接続と、macOS を実行しているデバイスで、セキュリティの種類などの設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-230">Apply a Wi-Fi connection and its settings, including the security type, on devices running macOS.</span></span>
- <span data-ttu-id="6c1ab-231">その他</span><span class="sxs-lookup"><span data-stu-id="6c1ab-231">And more</span></span>

<span data-ttu-id="6c1ab-232">[Microsoft Intune デバイス プロファイルは何ですか?](https://docs.microsoft.com/intune/device-profiles)プロファイルについて、プロファイルを作成する方法について説明するに最適の場所です。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-232">[What are Microsoft Intune device profiles?](https://docs.microsoft.com/intune/device-profiles) is a great place to read about profiles, see how to create a profile, and more.</span></span>

<span data-ttu-id="6c1ab-p131">注意してください、小規模、段階的なアプローチを使用します。パイロットまたはテストのグループにプロファイルを割り当てます。次に、パイロット グループをさらにプロファイルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p131">Remember, start small, and use a staged approach. Assign the profile to a pilot or test group. Then, assign the profile to more pilot groups.</span></span>

## <a name="step-8-get-to-know-the-other-features"></a><span data-ttu-id="6c1ab-236">手順 8: を取得、その他の機能を理解するには</span><span class="sxs-lookup"><span data-stu-id="6c1ab-236">Step 8: Get to know the other features</span></span>

<span data-ttu-id="6c1ab-p132">Intune では、強力なサービスと多くの機能が含まれています。Intune を使用して行うことができます他のいくつかのタスクを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p132">Intune is a powerful service, and includes many features. Here are some other tasks you can do using Intune:</span></span>

- <span data-ttu-id="6c1ab-239">Windows[デバイス](https://docs.microsoft.com/intune/windows-update-for-business-configure)でソフトウェアおよびアップデートを管理する & [の Pc](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)、および[iOS](https://docs.microsoft.com/intune/software-updates-ios)デバイス</span><span class="sxs-lookup"><span data-stu-id="6c1ab-239">Manage software and updates on Windows [devices](https://docs.microsoft.com/intune/windows-update-for-business-configure) & [PCs](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune), and [iOS](https://docs.microsoft.com/intune/software-updates-ios) devices</span></span>
- <span data-ttu-id="6c1ab-240">[Windows Defender 高度な脅威保護 (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) 、10 の Windows デバイスで有効にして、SharePoint または Exchange Online などの企業リソースへのアクセスを保護するために準拠し、条件付きのアクセスを使用してください</span><span class="sxs-lookup"><span data-stu-id="6c1ab-240">Turn on [Windows Defender Advanced Threat Protection (ATP)](https://docs.microsoft.com/intune/advanced-threat-protection) on your Windows 10 devices, and use compliance and conditional access to protect access to corporate resources, such as SharePoint or Exchange Online</span></span>
- <span data-ttu-id="6c1ab-241">[見張り](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector)、[シマンテック社](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)では、他の防御のモバイル脅威のパートナーを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-241">Use [Lookout](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector), [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector), and other mobile defense threat partners</span></span>
- <span data-ttu-id="6c1ab-242">発行し、証明書を書き換えるには、[パートナーの証明書機関 (CA)](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview)を追加します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-242">Add a [partner certificate authority (CA)](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) to issue and renew certificates</span></span>
- <span data-ttu-id="6c1ab-243">企業ポータル アプリケーション、取得するアプリケーションなどの[、エンド ・ ユーザーに提供するガイダンス](https://docs.microsoft.com/intune/end-user-educate)</span><span class="sxs-lookup"><span data-stu-id="6c1ab-243">[Provide guidance to your end users](https://docs.microsoft.com/intune/end-user-educate) on the Company Portal app, getting apps, and more</span></span>
- <span data-ttu-id="6c1ab-p133">モニター[アプリケーション](https://docs.microsoft.com/intune/apps-monitor)、[デバイスのコンプライアンス](https://docs.microsoft.com/intune/compliance-policy-monitor)を監視、モニター[構成のプロファイル](https://docs.microsoft.com/intune/compliance-policy-monitor)、および監査ログを使用して複数の遠隔測定します。[Intune データ ウェアハウス](https://docs.microsoft.com/intune/reports-nav-create-intune-reports)に接続し、レポートのニーズをさらに多くの BI の電源を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p133">Monitor [apps](https://docs.microsoft.com/intune/apps-monitor), monitor [device compliance](https://docs.microsoft.com/intune/compliance-policy-monitor), monitor [configuration profiles](https://docs.microsoft.com/intune/compliance-policy-monitor), and more telemetry using the audit logs. You can also connect to the [Intune Data Warehouse](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) and use Power BI for even more reporting needs.</span></span>


## <a name="identity-and-device-access-recommendations"></a><span data-ttu-id="6c1ab-246">Id とデバイスのアクセスに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="6c1ab-246">Identity and device access recommendations</span></span>

<span data-ttu-id="6c1ab-p134">マイクロソフトでは、一連の安全性と生産性の高い従業員を確保するのには[id とデバイスのアクセス](microsoft-365-policies-configurations.md)に関する推奨事項を提供します。デバイスへのアクセスの推奨事項と設定をこの段階では以下の手順の文書で使用します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-p134">Microsoft provides a set of recommendations for [identity and device access](microsoft-365-policies-configurations.md) to ensure a secure and productive workforce. For device access, use the recommendations and settings in the following articles along with the steps in this phase:</span></span>

- [<span data-ttu-id="6c1ab-249">前提条件</span><span class="sxs-lookup"><span data-stu-id="6c1ab-249">Prerequisites</span></span>](identity-access-prerequisites.md)
- [<span data-ttu-id="6c1ab-250">共通 ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="6c1ab-250">Common identity and device access policies</span></span>](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="6c1ab-251">Microsoft での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="6c1ab-251">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="6c1ab-252">マイクロソフトの IT 専門家の計画し、これらのリソースでは、EMS とデバイスの管理の展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-252">Learn how IT experts at Microsoft planned for and deployed EMS and device management with these resources:</span></span>

- [<span data-ttu-id="6c1ab-253">Enterprise Mobility + Security による最新のモバイル生産性の管理</span><span class="sxs-lookup"><span data-stu-id="6c1ab-253">Managing modern mobile productivity with Enterprise Mobility + Security</span></span>](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security)
- [<span data-ttu-id="6c1ab-254">Microsoft Intune を使用して Windows 10 デバイスでの作業につながる</span><span class="sxs-lookup"><span data-stu-id="6c1ab-254">Connecting to work on your Windows 10 device with Microsoft Intune</span></span>](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune)
- [<span data-ttu-id="6c1ab-255">Microsoft での iOS、OS X、Android デバイスによる業務効率化を可能にする</span><span class="sxs-lookup"><span data-stu-id="6c1ab-255">Enabling mobile productivity for iOS, OS X, and Android devices at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft)

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="6c1ab-256">Contoso 社での Microsoft 365 Enterprise の活用方法</span><span class="sxs-lookup"><span data-stu-id="6c1ab-256">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="6c1ab-257">Microsoft 365 で[、モバイル デバイスの管理インフラストラクチャの展開](contoso-mdm.md)を Contoso 社架空ですが、代表的な多国籍企業、クラウドのサービスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6c1ab-257">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed their mobile device management infrastructure](contoso-mdm.md) with Microsoft 365 cloud services.</span></span>

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="6c1ab-258">次の手順</span><span class="sxs-lookup"><span data-stu-id="6c1ab-258">Next step</span></span>

[<span data-ttu-id="6c1ab-259">モバイル デバイス管理インフラストラクチャの終了条件</span><span class="sxs-lookup"><span data-stu-id="6c1ab-259">Mobile device management infrastructure exit criteria</span></span>](mobility-infrastructure-exit-criteria.md)

