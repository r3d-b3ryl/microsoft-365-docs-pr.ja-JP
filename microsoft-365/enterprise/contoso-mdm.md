---
title: Contoso 社のモバイル デバイス管理
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
description: Contoso 社が Microsoft 365 Enterprise で EMS を使用して、デバイスやデバイスで実行されるアプリをどのように管理しているかを説明します。
ms.openlocfilehash: e6b6f822a8c0ea26b3d899e3531653b19e225d65
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868990"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="8a7c1-103">Contoso 社のモバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="8a7c1-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="8a7c1-104">**概要:** Contoso 社が Microsoft 365 Enterprise で EMS を使用して、デバイスやデバイスで実行されるアプリをどのように管理しているかを説明します。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-104">**Summary:** Understand how Contoso uses EMS in Microsoft 365 Enterprise to manage its devices and the apps that run on them.</span></span>

<span data-ttu-id="8a7c1-105">Microsoft 365 Enterprise の Enterprise Mobility + Security (EMS) は、Microsoft Intune と一連の Azure サービスで構成されており、モバイル デバイスとアプリケーションの管理およびセキュリティをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-105">Enterprise Mobility + Security (EMS) in Microsoft 365 Enterprise consists of Microsoft Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="8a7c1-p101">Contoso 社にはモバイル端末を使用する従業員が多く在籍しており、Contoso 社の場所にオフィスがある者もいれば、オフィスを持たない者もいます。Contoso 社では、従業員の生産性を高めつつ、デバイス、デバイスに保存される Contoso 社のデータ、およびアプリケーションの動作に関して何らかの方法でセキュリティを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="8a7c1-108">計画</span><span class="sxs-lookup"><span data-stu-id="8a7c1-108">Plan</span></span>

<span data-ttu-id="8a7c1-109">Contoso 社は、Microsoft 365 Enterprise 向けのモバイル デバイス管理について分析した初期段階で、次の方法で Intune を使用することを確認しました。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-109">Early in the analysis of mobile device management for Microsoft 365 Enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="8a7c1-110">Exchange Online のメールとデータを保護し、モバイル デバイスから安全にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="8a7c1-111">Contoso 社の従業員向けに、BYOD (Bring your own Device) プログラムを実装します。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-111">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="8a7c1-112">Contoso 社の従業員向けに、組織が所有するスマート フォンや、用途が限定された共有タブレットを支給します。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="8a7c1-113">Contoso 社は、次の用途では Intune を使用しません。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-113">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="8a7c1-114">管理対象ではない公共のキオスクから従業員が Office 365 に安全にアクセスできるようにする。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-114">Allow employees to securely access Office 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="8a7c1-115">オンプレミスの Microsoft Exchange サーバーがなくなったことに伴い、オンプレミスのメールとデータを保護し、モバイル デバイスからこれらに安全にアクセスできるようにする。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="8a7c1-116">展開</span><span class="sxs-lookup"><span data-stu-id="8a7c1-116">Deploy</span></span>

<span data-ttu-id="8a7c1-117">Contoso 社は、次のようにモバイル デバイス管理インフラストラクチャをセットアップしています。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="8a7c1-118">Intune をモバイル デバイス管理 (MDM) 機関として設定し、Azure 上で Intune を使用してコンテンツとデバイスを管理しています。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-118">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="8a7c1-119">登録するデバイス グループ用の Azure AD グループ、および Intune 設定と条件付きアクセスのポリシーを作成しています。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-119">Created Azure AD groups for device groups for enrollment and Intune settings and conditional access policies</span></span>
- <span data-ttu-id="8a7c1-120">iPad、iMac、iPhone、および会社所有の iPhone ベースの電話を使用する従業員をサポートするため、Apple デバイス プラットフォームを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-120">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="8a7c1-121">Contoso 社では、独自の使用条件ポリシーを作成しており、Contoso 社の会社ポータルをモバイル デバイスにインストールする時に表示されるようになっています。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-121">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="8a7c1-122">未登録デバイスについては、一連のモバイル アプリケーション管理 (MAM) ポリシーにより、Office 365 サービスにアクセスするための認証が要求されます。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-122">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Office 365 services</span></span>
- <span data-ttu-id="8a7c1-123">以下のための Intune ポリシーが作成されています。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-123">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="8a7c1-124">許可されているアプリ</span><span class="sxs-lookup"><span data-stu-id="8a7c1-124">Allowed apps</span></span>
  - <span data-ttu-id="8a7c1-125">不正アクセスを防止するためのデバイスの暗号化</span><span class="sxs-lookup"><span data-stu-id="8a7c1-125">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="8a7c1-126">6 桁の暗証番号 (PIN) またはパスワード</span><span class="sxs-lookup"><span data-stu-id="8a7c1-126">A six-digit PIN or password</span></span>
  - <span data-ttu-id="8a7c1-127">休止状態によるタイムアウト時間</span><span class="sxs-lookup"><span data-stu-id="8a7c1-127">An inactivity timeout period</span></span>
  - <span data-ttu-id="8a7c1-128">Windows 10 デバイス上で Windows Defender を使用した、ウイルス対策とマルウェア保護、および署名の更新</span><span class="sxs-lookup"><span data-stu-id="8a7c1-128">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="8a7c1-129">最新のセキュリティ更新プログラムを含む Windows 10 デバイス上の自動更新</span><span class="sxs-lookup"><span data-stu-id="8a7c1-129">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="8a7c1-130">管理対象デバイスへの証明書のプッシュ</span><span class="sxs-lookup"><span data-stu-id="8a7c1-130">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="8a7c1-p102">ビジネス データと個人データの明確な分離。ユーザーまたは管理者は、画像、個人用メール アカウント、個人用ファイルなどの個人データはそのままにして、デバイスから会社のデータを選択的に消去できます。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="8a7c1-p103">これらの展開後に、Contoso 社は PC や会社所有のスマートフォンとタブレットを適切な Intune デバイス グループに追加して登録し、従業員向けに BYOD プログラムをロールアウトして従業員が個人用デバイスを登録できるようにしました。登録されたデバイスには Intune ポリシーが適用され、デバイスとそのアプリケーションは管理対象としてセキュリティ保護されています。未登録デバイスにはモバイル アプリケーション管理 (MAM) ポリシーが適用され、許可されているアプリケーションが指定されます。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

## <a name="next-step"></a><span data-ttu-id="8a7c1-136">次の手順</span><span class="sxs-lookup"><span data-stu-id="8a7c1-136">Next step</span></span>

<span data-ttu-id="8a7c1-137">Contoso 社が Microsoft 365 Enterprise の情報保護機能を利用して、重要なデジタル資産を組織全体でどのように分類、識別、保護しているかを[説明](contoso-info-protect.md)します。</span><span class="sxs-lookup"><span data-stu-id="8a7c1-137">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 Enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a7c1-138">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a7c1-138">See also</span></span>

[<span data-ttu-id="8a7c1-139">Microsoft 365 Enterprise のモバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="8a7c1-139">Mobile device management for Microsoft 365 Enterprise</span></span>](mobility-infrastructure.md)

[<span data-ttu-id="8a7c1-140">展開ガイド</span><span class="sxs-lookup"><span data-stu-id="8a7c1-140">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="8a7c1-141">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="8a7c1-141">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

