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
description: Contoso 社が microsoft 365 で microsoft Intune を使用して、自社のデバイスおよびそれらに対して実行されているアプリを管理する方法について説明します。
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753999"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="7761b-103">Contoso 社のモバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="7761b-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="7761b-104">Microsoft 365 for enterprise には、モバイルデバイスとアプリケーションの管理とセキュリティをサポートする Intune および Azure サービスのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="7761b-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="7761b-p101">Contoso 社には、多くのモバイル対応従業員がいます。Contoso 社の場所にオフィスがあり、一部にはオフィスがありません。Contoso 社は従業員の生産性を有効にする方法を必要としましたが、デバイス、これらのデバイスに格納されている Contoso データ、およびアプリケーションの動作を安全に保つ必要がありました。</span><span class="sxs-lookup"><span data-stu-id="7761b-p101">Contoso has many mobile-enabled employees. Some have offices in Contoso locations, and some have no offices. Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="7761b-108">計画</span><span class="sxs-lookup"><span data-stu-id="7761b-108">Plan</span></span>

<span data-ttu-id="7761b-109">Contoso 社は、Microsoft 365 for enterprise のモバイルデバイス管理の次の Intune ユースケースを特定しました。</span><span class="sxs-lookup"><span data-stu-id="7761b-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="7761b-110">Exchange Online の電子メールとデータを保護して、モバイルデバイスから安全にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="7761b-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="7761b-111">Contoso 社の従業員向けのデバイス (BYOD) プログラムを実装します。</span><span class="sxs-lookup"><span data-stu-id="7761b-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="7761b-112">Contoso 社の従業員に対して、組織が所有する電話と制限付きのタブレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7761b-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="7761b-113">Contoso 社は Intune を使用して次のことを行いません。</span><span class="sxs-lookup"><span data-stu-id="7761b-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="7761b-114">従業員が、管理されていないパブリックキオスクから Microsoft 365 に安全にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="7761b-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="7761b-115">オンプレミスの Microsoft Exchange サーバーが存在しないため、モバイルデバイスから安全にアクセスできるように、オンプレミスの電子メールとデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="7761b-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="7761b-116">展開</span><span class="sxs-lookup"><span data-stu-id="7761b-116">Deploy</span></span>

<span data-ttu-id="7761b-117">Contoso 社は、次のようにモバイル デバイス管理インフラストラクチャをセットアップしています。</span><span class="sxs-lookup"><span data-stu-id="7761b-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="7761b-118">モバイルデバイス管理 (MDM) 機関として Intune を設定し、Azure で Intune を使用してコンテンツを管理し、デバイスを管理する</span><span class="sxs-lookup"><span data-stu-id="7761b-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="7761b-119">登録および Intune の設定およびデバイスベースの条件付きアクセスポリシー用のデバイス用に、Azure Active Directory (Azure AD) グループを作成しました。</span><span class="sxs-lookup"><span data-stu-id="7761b-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="7761b-120">詳細については、「 [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7761b-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="7761b-121">Ipad、iMacs、および iPhones、および企業所有の iPhones を備えた従業員をサポートするための Apple デバイスプラットフォームを有効にしました。</span><span class="sxs-lookup"><span data-stu-id="7761b-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="7761b-122">Contoso 社では、独自の使用条件ポリシーを作成しており、Contoso 社の会社ポータルをモバイル デバイスにインストールする時に表示されるようになっています。</span><span class="sxs-lookup"><span data-stu-id="7761b-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="7761b-123">登録されていないデバイスの場合は、Microsoft 365 サービスへのアクセスの認証を必要とする一連のモバイルアプリケーション管理 (MAM) ポリシーを実装します。</span><span class="sxs-lookup"><span data-stu-id="7761b-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="7761b-124">以下のための Intune ポリシーが作成されています。</span><span class="sxs-lookup"><span data-stu-id="7761b-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="7761b-125">許可されたアプリ。</span><span class="sxs-lookup"><span data-stu-id="7761b-125">Allowed apps.</span></span>
  - <span data-ttu-id="7761b-126">許可されていないアクセスを防止するためのデバイスの暗号化。</span><span class="sxs-lookup"><span data-stu-id="7761b-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="7761b-127">6桁の PIN またはパスワード。</span><span class="sxs-lookup"><span data-stu-id="7761b-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="7761b-128">非アクティブなタイムアウト時間。</span><span class="sxs-lookup"><span data-stu-id="7761b-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="7761b-129">Windows 10 デバイス上で Windows Defender を使用して、ウイルス対策およびマルウェア対策および署名の更新を行います。</span><span class="sxs-lookup"><span data-stu-id="7761b-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="7761b-130">最新のセキュリティ更新プログラムが含まれている Windows 10 デバイスでの自動更新。</span><span class="sxs-lookup"><span data-stu-id="7761b-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="7761b-131">管理対象デバイスへの証明書のプッシュ。</span><span class="sxs-lookup"><span data-stu-id="7761b-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="7761b-p102">ビジネス データと個人データの明確な分離。ユーザーまたは管理者は、画像、個人用メール アカウント、個人用ファイルなどの個人データはそのままにして、デバイスから会社のデータを選択的に消去できます。</span><span class="sxs-lookup"><span data-stu-id="7761b-p102">A clear separation of business and personal data. Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="7761b-134">Contoso 社は、適切な Intune デバイスグループに追加することによって、展開済みの Pc と会社所有のスマートフォンおよびタブレットを登録しました。</span><span class="sxs-lookup"><span data-stu-id="7761b-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="7761b-135">また、従業員が個人デバイスを登録するための BYOD プログラムも設定しました。</span><span class="sxs-lookup"><span data-stu-id="7761b-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="7761b-136">登録済みデバイスは Intune ポリシーを受信します。これにより、管理対象およびセキュリティで保護されたデバイスとそのアプリケーションが生成されます。</span><span class="sxs-lookup"><span data-stu-id="7761b-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="7761b-137">登録されていないデバイスには、許可されたアプリケーションを指定するモバイルアプリケーション管理 (MAM) ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="7761b-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="7761b-138">ここでは、Contoso モバイルデバイス管理の展開アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7761b-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Contoso モバイルデバイス管理の展開インフラストラクチャ](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="7761b-140">次のステップ</span><span class="sxs-lookup"><span data-stu-id="7761b-140">Next step</span></span>

<span data-ttu-id="7761b-141">Contoso 社が Microsoft 365 の [情報保護機能](contoso-info-protect.md) を使用して、企業全体で重要なデジタル資産を分類、識別、保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7761b-141">Learn how Contoso uses the [information protection capabilities](contoso-info-protect.md) of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="7761b-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="7761b-142">See also</span></span>

[<span data-ttu-id="7761b-143">Microsoft 365 のデバイス管理</span><span class="sxs-lookup"><span data-stu-id="7761b-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="7761b-144">Microsoft 365 for enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="7761b-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7761b-145">テスト ラボ ガイド</span><span class="sxs-lookup"><span data-stu-id="7761b-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

