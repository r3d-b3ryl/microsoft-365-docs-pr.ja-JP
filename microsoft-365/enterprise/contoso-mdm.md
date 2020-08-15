---
title: Contoso 社のモバイル デバイス管理
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社が microsoft 365 で microsoft Intune を使用して、自社のデバイスおよびそれらに対して実行されているアプリを管理する方法について説明します。
ms.openlocfilehash: 40d9473bcadfa636f6fd2b2c6c861c27dae8497c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685844"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="e1cf4-103">Contoso 社のモバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="e1cf4-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="e1cf4-104">Microsoft 365 for enterprise には、モバイルデバイスとアプリケーションの管理とセキュリティをサポートするための、Intune および Azure サービスのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-104">Microsoft 365 for enterprise includes Intune and a set of Azure services to support mobile device and application management and security.</span></span>

<span data-ttu-id="e1cf4-p101">Contoso 社にはモバイル端末を使用する従業員が多く在籍しており、Contoso 社の場所にオフィスがある者もいれば、オフィスを持たない者もいます。Contoso 社では、従業員の生産性を高めつつ、デバイス、デバイスに保存される Contoso 社のデータ、およびアプリケーションの動作に関して何らかの方法でセキュリティを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-p101">Contoso has many mobile-enabled employees, some of which have offices in Contoso locations and some of which have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="e1cf4-107">計画</span><span class="sxs-lookup"><span data-stu-id="e1cf4-107">Plan</span></span>

<span data-ttu-id="e1cf4-108">Microsoft 365 for enterprise のモバイルデバイス管理の分析の初期段階では、Contoso 社は次の Intune ユースケースを特定しました。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-108">Early in the analysis of mobile device management for Microsoft 365 for enterprise, Contoso identified the following Intune use cases:</span></span>

- <span data-ttu-id="e1cf4-109">Exchange Online のメールとデータを保護し、モバイル デバイスから安全にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-109">Protect Exchange Online email and data so it can be safely accessed by mobile devices</span></span>
- <span data-ttu-id="e1cf4-110">Contoso 社の従業員向けに、BYOD (Bring your own Device) プログラムを実装します。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-110">Implement a bring your own device (BYOD) program for Contoso employees</span></span>
- <span data-ttu-id="e1cf4-111">Contoso 社の従業員向けに、組織が所有するスマート フォンや、用途が限定された共有タブレットを支給します。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-111">Issue organization-owned phones and limited-use shared tablets to Contoso employees</span></span>

<span data-ttu-id="e1cf4-112">Contoso 社は、次の用途では Intune を使用しません。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-112">Contoso is not using Intune to:</span></span>

- <span data-ttu-id="e1cf4-113">従業員が管理されていないパブリックキオスクから Microsoft 365 に安全にアクセスできるようにする</span><span class="sxs-lookup"><span data-stu-id="e1cf4-113">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk</span></span>
- <span data-ttu-id="e1cf4-114">オンプレミスの Microsoft Exchange サーバーがなくなったことに伴い、オンプレミスのメールとデータを保護し、モバイル デバイスからこれらに安全にアクセスできるようにする。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-114">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no longer on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="e1cf4-115">展開</span><span class="sxs-lookup"><span data-stu-id="e1cf4-115">Deploy</span></span>

<span data-ttu-id="e1cf4-116">Contoso 社は、次のようにモバイル デバイス管理インフラストラクチャをセットアップしています。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-116">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="e1cf4-117">Intune をモバイル デバイス管理 (MDM) 機関として設定し、Azure 上で Intune を使用してコンテンツとデバイスを管理しています。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-117">Set Intune as the Mobile Device Management (MDM) authority and are using Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="e1cf4-118">登録するデバイス用の Azure AD グループ、および Intune 設定とデバイスベースの条件付きアクセス ポリシーを作成しています。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-118">Created Azure AD groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="e1cf4-119">詳細については、「[Contoso 社の条件付きアクセス ポリシー](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-119">See [Contoso's Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access) for more information.</span></span>

- <span data-ttu-id="e1cf4-120">iPad、iMac、iPhone、および会社所有の iPhone ベースの電話を使用する従業員をサポートするため、Apple デバイス プラットフォームを有効にしています。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-120">Enabled the Apple device platform to support employees with iPads, iMacs, iPhones, and for iPhone-based corporate-owned phones</span></span>
- <span data-ttu-id="e1cf4-121">Contoso 社では、独自の使用条件ポリシーを作成しており、Contoso 社の会社ポータルをモバイル デバイスにインストールする時に表示されるようになっています。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-121">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="e1cf4-122">登録されていないデバイスの場合、Microsoft 365 サービスへのアクセスの認証を必要とするモバイルアプリケーション管理 (MAM) ポリシーのセット</span><span class="sxs-lookup"><span data-stu-id="e1cf4-122">For devices that are not enrolled, a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="e1cf4-123">以下のための Intune ポリシーが作成されています。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-123">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="e1cf4-124">許可されているアプリ</span><span class="sxs-lookup"><span data-stu-id="e1cf4-124">Allowed apps</span></span>
  - <span data-ttu-id="e1cf4-125">不正アクセスを防止するためのデバイスの暗号化</span><span class="sxs-lookup"><span data-stu-id="e1cf4-125">Device encryption to help prevent unauthorized access</span></span>
  - <span data-ttu-id="e1cf4-126">6 桁の暗証番号 (PIN) またはパスワード</span><span class="sxs-lookup"><span data-stu-id="e1cf4-126">A six-digit PIN or password</span></span>
  - <span data-ttu-id="e1cf4-127">休止状態によるタイムアウト時間</span><span class="sxs-lookup"><span data-stu-id="e1cf4-127">An inactivity timeout period</span></span>
  - <span data-ttu-id="e1cf4-128">Windows 10 デバイス上で Windows Defender を使用した、ウイルス対策とマルウェア保護、および署名の更新</span><span class="sxs-lookup"><span data-stu-id="e1cf4-128">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices</span></span>
  - <span data-ttu-id="e1cf4-129">最新のセキュリティ更新プログラムを含む Windows 10 デバイス上の自動更新</span><span class="sxs-lookup"><span data-stu-id="e1cf4-129">Automatic updates on Windows 10 devices that include the latest security updates</span></span>
  - <span data-ttu-id="e1cf4-130">管理対象デバイスへの証明書のプッシュ</span><span class="sxs-lookup"><span data-stu-id="e1cf4-130">Pushing certificates to managed devices</span></span>
  - <span data-ttu-id="e1cf4-p102">ビジネス データと個人データの明確な分離。ユーザーまたは管理者は、画像、個人用メール アカウント、個人用ファイルなどの個人データはそのままにして、デバイスから会社のデータを選択的に消去できます。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="e1cf4-p103">これらの展開後に、Contoso 社は PC や会社所有のスマートフォンとタブレットを適切な Intune デバイス グループに追加して登録し、従業員向けに BYOD プログラムをロールアウトして従業員が個人用デバイスを登録できるようにしました。登録されたデバイスには Intune ポリシーが適用され、デバイスとそのアプリケーションは管理対象としてセキュリティ保護されています。未登録デバイスにはモバイル アプリケーション管理 (MAM) ポリシーが適用され、許可されているアプリケーションが指定されます。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-p103">Once deployed, Contoso enrolled PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups and rolled out a BYOD program for employees to enroll their personal devices. Enrolled devices received Intune policies, resulting in managed and secured devices and their applications. Devices that are not enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="e1cf4-136">次に Contoso 社のモバイル デバイス管理展開アーキテクチャを示します。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-136">Here is Contoso's mobile device management deployment architecture.</span></span>

![Contoso 社のモバイル デバイス管理展開インフラストラクチャ](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="e1cf4-138">次の手順</span><span class="sxs-lookup"><span data-stu-id="e1cf4-138">Next step</span></span>

<span data-ttu-id="e1cf4-139">Contoso 社が Microsoft 365 の情報保護機能を使用して、企業全体で重要なデジタル資産を分類、識別、保護する方法に[ついて説明](contoso-info-protect.md)します。</span><span class="sxs-lookup"><span data-stu-id="e1cf4-139">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1cf4-140">関連項目</span><span class="sxs-lookup"><span data-stu-id="e1cf4-140">See also</span></span>

[<span data-ttu-id="e1cf4-141">Microsoft 365 のデバイス管理</span><span class="sxs-lookup"><span data-stu-id="e1cf4-141">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="e1cf4-142">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="e1cf4-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e1cf4-143">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="e1cf4-143">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

