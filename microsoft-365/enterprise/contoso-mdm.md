---
title: Contoso 社のモバイル デバイス管理
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 社がエンタープライズ向Microsoft Intune Microsoft 365デバイスとそのデバイスで実行するアプリを管理する方法について説明します。
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753999"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="5db06-103">Contoso 社のモバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="5db06-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="5db06-104">Microsoft 365には、Intune と、モバイル デバイスとアプリケーションの管理とセキュリティをサポートする一連の Azure サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5db06-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="5db06-105">Contoso には、モバイル対応の従業員が多数います。</span><span class="sxs-lookup"><span data-stu-id="5db06-105">Contoso has many mobile-enabled employees.</span></span> <span data-ttu-id="5db06-106">一部のオフィスは Contoso の場所に、一部のオフィスにはオフィスはありません。</span><span class="sxs-lookup"><span data-stu-id="5db06-106">Some have offices in Contoso locations, and some have no offices.</span></span> <span data-ttu-id="5db06-107">Contoso 社では、従業員の生産性を有効にし、デバイス、それらのデバイスに保存されている Contoso データ、およびアプリケーションの動作を安全に保つ方法が必要でした。</span><span class="sxs-lookup"><span data-stu-id="5db06-107">Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="5db06-108">計画</span><span class="sxs-lookup"><span data-stu-id="5db06-108">Plan</span></span>

<span data-ttu-id="5db06-109">Contoso 社は、エンタープライズ向けモバイル デバイス管理の次の Intune Microsoft 365を特定しました。</span><span class="sxs-lookup"><span data-stu-id="5db06-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="5db06-110">メールExchange Onlineデータを保護して、モバイル デバイスから安全にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5db06-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="5db06-111">Contoso の従業員に対して、自分でデバイスを持ち込む (BYOD) プログラムを実装します。</span><span class="sxs-lookup"><span data-stu-id="5db06-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="5db06-112">Contoso の従業員に組織所有の電話と使用制限付き共有タブレットを発行します。</span><span class="sxs-lookup"><span data-stu-id="5db06-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="5db06-113">Contoso は Intune を使用して次の条件を設定します。</span><span class="sxs-lookup"><span data-stu-id="5db06-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="5db06-114">従業員が管理されていない公開キオスクからMicrosoft 365にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5db06-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="5db06-115">オンプレミスの Microsoft Exchange サーバーがないので、モバイル デバイスから安全にアクセスできるよう、オンプレミスの電子メールとデータをExchangeします。</span><span class="sxs-lookup"><span data-stu-id="5db06-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="5db06-116">展開</span><span class="sxs-lookup"><span data-stu-id="5db06-116">Deploy</span></span>

<span data-ttu-id="5db06-117">Contoso 社は、次のようにモバイル デバイス管理インフラストラクチャをセットアップしています。</span><span class="sxs-lookup"><span data-stu-id="5db06-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="5db06-118">Intune をモバイル デバイス管理 (MDM) 機関として設定し、Intune on Azure を使用してコンテンツを管理し、デバイスを管理する</span><span class="sxs-lookup"><span data-stu-id="5db06-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="5db06-119">登録Azure Active Directory Intune のAD条件付きアクセス ポリシーのデバイス用に作成されたグループ (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="5db06-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="5db06-120">詳細については [、「Contoso 条件付きアクセス ポリシー」を参照してください](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。</span><span class="sxs-lookup"><span data-stu-id="5db06-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="5db06-121">Apple デバイス プラットフォームで、iPad、iMac、および iPhone、および企業所有の iPhone で従業員をサポートする機能を有効にしました</span><span class="sxs-lookup"><span data-stu-id="5db06-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="5db06-122">Contoso 社では、独自の使用条件ポリシーを作成しており、Contoso 社の会社ポータルをモバイル デバイスにインストールする時に表示されるようになっています。</span><span class="sxs-lookup"><span data-stu-id="5db06-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="5db06-123">登録されていないデバイスの場合は、一連のモバイル アプリケーション管理 (MAM) ポリシーを実装して、サービスへのアクセスに認証をMicrosoft 365しました</span><span class="sxs-lookup"><span data-stu-id="5db06-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="5db06-124">以下のための Intune ポリシーが作成されています。</span><span class="sxs-lookup"><span data-stu-id="5db06-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="5db06-125">許可されているアプリ。</span><span class="sxs-lookup"><span data-stu-id="5db06-125">Allowed apps.</span></span>
  - <span data-ttu-id="5db06-126">承認されていないアクセスを防止するためのデバイスの暗号化。</span><span class="sxs-lookup"><span data-stu-id="5db06-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="5db06-127">6 桁の PIN またはパスワード。</span><span class="sxs-lookup"><span data-stu-id="5db06-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="5db06-128">非アクティブ タイムアウト期間。</span><span class="sxs-lookup"><span data-stu-id="5db06-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="5db06-129">ウイルス対策とマルウェアの保護、およびデバイス上のWindows Defender署名Windows 10更新。</span><span class="sxs-lookup"><span data-stu-id="5db06-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="5db06-130">最新のセキュリティ更新Windows 10含むデバイスの自動更新。</span><span class="sxs-lookup"><span data-stu-id="5db06-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="5db06-131">管理対象デバイスへの証明書のプッシュ。</span><span class="sxs-lookup"><span data-stu-id="5db06-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="5db06-p102">ビジネス データと個人データの明確な分離。ユーザーまたは管理者は、画像、個人用メール アカウント、個人用ファイルなどの個人データはそのままにして、デバイスから会社のデータを選択的に消去できます。</span><span class="sxs-lookup"><span data-stu-id="5db06-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="5db06-134">Contoso 社は、展開された PC と会社所有のスマートフォンとタブレットを適切な Intune デバイス グループに追加して登録しました。</span><span class="sxs-lookup"><span data-stu-id="5db06-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="5db06-135">また、従業員が個人用デバイスを登録する BYOD プログラムも確立しました。</span><span class="sxs-lookup"><span data-stu-id="5db06-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="5db06-136">登録されたデバイスは Intune ポリシーを受け取り、その結果、管理対象デバイスとセキュリティで保護されたデバイスとそのアプリケーションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5db06-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="5db06-137">登録されていないデバイスには、許可されたアプリケーションを指定するモバイル アプリケーション管理 (MAM) ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="5db06-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="5db06-138">Contoso モバイル デバイス管理の展開アーキテクチャを次に示します。</span><span class="sxs-lookup"><span data-stu-id="5db06-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Contoso モバイル デバイス管理展開インフラストラクチャ](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="5db06-140">次の手順</span><span class="sxs-lookup"><span data-stu-id="5db06-140">Next step</span></span>

<span data-ttu-id="5db06-141">Contoso 社がエンタープライズ向[け](contoso-info-protect.md)Microsoft 365の情報保護機能を使用して、組織全体で重要なデジタル資産を分類、識別、および保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5db06-141">Learn how Contoso uses the [information protection capabilities](contoso-info-protect.md) of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="5db06-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="5db06-142">See also</span></span>

[<span data-ttu-id="5db06-143">デバイスの管理Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5db06-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="5db06-144">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="5db06-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5db06-145">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="5db06-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

