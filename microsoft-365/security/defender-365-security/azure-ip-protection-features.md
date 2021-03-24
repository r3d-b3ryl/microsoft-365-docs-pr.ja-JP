---
title: Azure Information Protection の保護機能が既存のテナントに展開される
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: この記事では、Azure Information Protection の保護機能に対して展開される変更について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77d45c8521e67c480b9e5557b05eed8ba5dd2645
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065459"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a><span data-ttu-id="5d265-103">Azure Information Protection の保護機能が既存のテナントに展開される</span><span class="sxs-lookup"><span data-stu-id="5d265-103">Protection features in Azure Information Protection rolling out to existing tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5d265-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="5d265-104">**Applies to**</span></span>
- [<span data-ttu-id="5d265-105">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="5d265-105">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5d265-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5d265-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5d265-107">2018 年 7 月から、Azure Information Protection の対象テナントすべてが Azure Information Protection の保護機能を既定で有効にします。</span><span class="sxs-lookup"><span data-stu-id="5d265-107">To help with the initial step in protecting your information, starting July 2018 all Azure Information Protection eligible tenants will have the protection features in Azure Information Protection turned on by default.</span></span> <span data-ttu-id="5d265-108">Azure Information Protection の保護機能は、以前は 365 Office Rights Management または Azure RMS として知られています。</span><span class="sxs-lookup"><span data-stu-id="5d265-108">The protection features in Azure Information Protection were formerly known in Office 365 as Rights Management or Azure RMS.</span></span> <span data-ttu-id="5d265-109">組織に E3 サービス プランOffice高いサービス プランがある場合は、これらの機能を展開するときに Azure Information Protection を通じて情報の保護を開始します。</span><span class="sxs-lookup"><span data-stu-id="5d265-109">If your organization has an Office E3 service plan or a higher service plan you will now get a head start protecting information through Azure Information Protection when we roll out these features.</span></span>

## <a name="changes-beginning-july-1-2018"></a><span data-ttu-id="5d265-110">2018 年 7 月 1 日から変更</span><span class="sxs-lookup"><span data-stu-id="5d265-110">Changes beginning July 1, 2018</span></span>

<span data-ttu-id="5d265-111">2018 年 7 月 1 日より、Microsoft は Azure Information Protection の保護機能をすべての組織で有効にし、次のいずれかのサブスクリプション プランを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d265-111">Starting July 1, 2018, Microsoft will enable the protection capability in Azure Information Protection for all organizations with one of the following subscription plans:</span></span>

- <span data-ttu-id="5d265-112">Office 365 メッセージ暗号化は、Office 365 E3 および E5、Microsoft E3 と E5、Office 365 A1、A3、および A5、および Office 365 G3 および G5 の一部として提供されます。</span><span class="sxs-lookup"><span data-stu-id="5d265-112">Office 365 Message Encryption is offered as part of Office 365 E3 and E5, Microsoft E3 and E5, Office 365 A1, A3, and A5, and Office 365 G3 and G5.</span></span> <span data-ttu-id="5d265-113">Azure Information Protection を利用した新しい保護機能を受け取る場合は、追加のライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="5d265-113">You do not need additional licenses to receive the new protection capabilities powered by Azure Information Protection.</span></span>

- <span data-ttu-id="5d265-114">Azure Information Protection Plan 1 を次のプランに追加して、新しい Office 365 メッセージ暗号化機能 (Exchange Online プラン 1、Exchange Online プラン 2、Office 365 F1、Microsoft 365 Business Basic、Microsoft 365 Business Standard、または Office 365 Enterprise E1) を受信できます。</span><span class="sxs-lookup"><span data-stu-id="5d265-114">You can also add Azure Information Protection Plan 1 to the following plans to receive the new Office 365 Message Encryption capabilities: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard, or Office 365 Enterprise E1.</span></span>

- <span data-ttu-id="5d265-115">365 Message Encryption Officeを利用する各ユーザーは、この機能の対象となるライセンスを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d265-115">Each user benefiting from Office 365 Message Encryption needs to be licensed to be covered by the feature.</span></span>

- <span data-ttu-id="5d265-116">完全な一覧については [、「Exchange Online サービス](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) の説明」を参照Office 365 Message Encryption です。</span><span class="sxs-lookup"><span data-stu-id="5d265-116">For the full list, see the [Exchange Online service descriptions](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) for Office 365 Message Encryption.</span></span>

<span data-ttu-id="5d265-117">テナント管理者は、365 管理者ポータルの Office状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5d265-117">Tenant administrators can check the protection status in the Office 365 administrator portal.</span></span>

![365 の権限管理がアクティブOfficeスクリーンショット。](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a><span data-ttu-id="5d265-119">この変更を行う理由</span><span class="sxs-lookup"><span data-stu-id="5d265-119">Why are we making this change?</span></span>

<span data-ttu-id="5d265-120">Office 365 メッセージ暗号化は、Azure Information Protection の保護機能を活用します。</span><span class="sxs-lookup"><span data-stu-id="5d265-120">Office 365 Message Encryption leverages the protection capabilities in Azure Information Protection.</span></span> <span data-ttu-id="5d265-121">Office 365 Message Encryption に対する最近の改善と、Microsoft 365 の情報保護への広範な投資の中心で、組織が保護機能を有効にし、使用しやすくなっています。これまで、暗号化テクノロジのセットアップは困難でした。</span><span class="sxs-lookup"><span data-stu-id="5d265-121">At the heart of the recent improvements to Office 365 Message Encryption and our broader investments to information protection in Microsoft 365, we are making it easier for organizations to turn on and use our protection capabilities, as historically, encryption technologies have been difficult to set up.</span></span> <span data-ttu-id="5d265-122">Azure Information Protection の保護機能を既定で有効にすることで、機密データの保護をすばやく開始できます。</span><span class="sxs-lookup"><span data-stu-id="5d265-122">By turning on the protection features in Azure Information Protection by default, you can quickly get started to protect your sensitive data.</span></span>

## <a name="does-this-impact-me"></a><span data-ttu-id="5d265-123">これは私に影響を与えますか?</span><span class="sxs-lookup"><span data-stu-id="5d265-123">Does this impact me?</span></span>

<span data-ttu-id="5d265-124">組織が 365 ライセンスの対象Office購入した場合、テナントはこの変更の影響を受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d265-124">If your organization has purchased an eligible Office 365 license, then your tenant will be impacted by this change.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d265-125">オンプレミス環境で Active Directory Rights Management サービス (AD RMS) を使用している場合は、この変更を今後 30 日以内に展開する前に、直ちにこの変更をオプトアウトするか、Azure Information Protection に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d265-125">If you're using Active Directory Rights Management Services (AD RMS) in your on-premises environment, you must either opt-out of this change immediately or migrate to Azure Information Protection before we roll out this change within the next 30 days.</span></span> <span data-ttu-id="5d265-126">オプトアウトの方法の詳細については、「RMS を使用ADオプトアウトする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d265-126">For information on how to opt-out, see "I use AD RMS, how do I opt out?"</span></span> <span data-ttu-id="5d265-127">」で説明する手順に従ってローカライズされたファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5d265-127">later in this article.</span></span> <span data-ttu-id="5d265-128">移行する場合は、「RMS から Azure Information Protection への移行 [AD」を参照してください](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)。</span><span class="sxs-lookup"><span data-stu-id="5d265-128">If you prefer to migrate, see [Migrating from AD RMS to Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span>

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a><span data-ttu-id="5d265-129">Azure Information Protection を (RMS) Active Directory Rights Management サービス使用ADできますか?</span><span class="sxs-lookup"><span data-stu-id="5d265-129">Can I use Azure Information Protection with Active Directory Rights Management Services (AD RMS)?</span></span>

<span data-ttu-id="5d265-130">いいえ。</span><span class="sxs-lookup"><span data-stu-id="5d265-130">No.</span></span> <span data-ttu-id="5d265-131">これは、サポートされている展開シナリオではありません。</span><span class="sxs-lookup"><span data-stu-id="5d265-131">This is not a supported deployment scenario.</span></span> <span data-ttu-id="5d265-132">追加のオプトアウト手順を実行しない場合、一部のコンピューターは Azure Rights Management サービスの使用を自動的に開始し、RMS クラスターにAD可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5d265-132">Without taking the additional opt-out steps, some computers might automatically start using the Azure Rights Management service and also connect to your AD RMS cluster.</span></span> <span data-ttu-id="5d265-133">このシナリオはサポートされていないので、結果が不当なので、これらの新機能を展開する前に、今後 30 日以内にこの変更をオプトアウトすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="5d265-133">This scenario isn't supported and has unreliable results, so it's important that you opt out of this change within the next 30 days before we roll out these new features.</span></span> <span data-ttu-id="5d265-134">オプトアウトの方法の詳細については、「RMS を使用ADオプトアウトする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d265-134">For information on how to opt-out, see "I use AD RMS, how do I opt out?"</span></span> <span data-ttu-id="5d265-135">」で説明する手順に従ってローカライズされたファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5d265-135">later in this article.</span></span> <span data-ttu-id="5d265-136">移行する場合は、「RMS から Azure Information Protection への移行 [AD」を参照してください。](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="5d265-136">If you prefer to migrate, see [Migrating from AD RMS to Azure Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span></span>

## <a name="how-do-i-know-if-im-using-ad-rms"></a><span data-ttu-id="5d265-137">RMS を使用している場合のAD方法</span><span class="sxs-lookup"><span data-stu-id="5d265-137">How do I know if I'm using AD RMS?</span></span>

<span data-ttu-id="5d265-138">ACTIVE DIRECTORY RIGHTS MANAGEMENT サービス [(AD RMS)](/azure/information-protection/deploy-use/prepare-environment-adrms) を持っている場合は、「Azure Rights Management の環境を準備する」の手順を使用して、RMS をADしてください。</span><span class="sxs-lookup"><span data-stu-id="5d265-138">Use these instructions from [Preparing the environment for Azure Rights Management when you also have Active Directory Rights Management Services (AD RMS)](/azure/information-protection/deploy-use/prepare-environment-adrms) to check if you have deployed AD RMS:</span></span>

1. <span data-ttu-id="5d265-139">オプションですが、ほとんどの RMS 展開ADサービス接続ポイント (SCP) を Active Directory に発行して、ドメイン コンピューターが RMS クラスターを検出ADします。</span><span class="sxs-lookup"><span data-stu-id="5d265-139">Although optional, most AD RMS deployments publish the service connection point (SCP) to Active Directory so that domain computers can discover the AD RMS cluster.</span></span>

   <span data-ttu-id="5d265-140">ADSI Edit を使用して、Active Directory で公開されている SCP を持っているかどうかを確認します。CN=Configuration [server name]、CN=Services、CN=RightsManagementServices、CN=SCP</span><span class="sxs-lookup"><span data-stu-id="5d265-140">Use ADSI Edit to see whether you have an SCP published in Active Directory: CN=Configuration [server name], CN=Services, CN=RightsManagementServices, CN=SCP</span></span>

2. <span data-ttu-id="5d265-141">SCP を使用していない場合、AD RMS クラスターに接続する Windows コンピューターは、Windows レジストリを使用してクライアント側のサービス検出またはライセンスリダイレクト用に構成する必要があります。 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation`</span><span class="sxs-lookup"><span data-stu-id="5d265-141">If you are not using an SCP, Windows computers that connect to an AD RMS cluster must be configured for client-side service discovery or licensing redirection by using the Windows registry: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation`.</span></span>

<span data-ttu-id="5d265-142">これらのレジストリ構成の詳細については [、「Windows](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) レジストリを使用したクライアント側サービス検出の有効化」および「ライセンス サーバー トラフィックのリダイレクト」 [を参照してください](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)。</span><span class="sxs-lookup"><span data-stu-id="5d265-142">For more information about these registry configurations, see [Enabling client-side service discovery by using the Windows registry](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) and [Redirecting licensing server traffic](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).</span></span>

## <a name="i-use-ad-rms-how-do-i-opt-out"></a><span data-ttu-id="5d265-143">RMS をAD、オプトアウトする方法は?</span><span class="sxs-lookup"><span data-stu-id="5d265-143">I use AD RMS, how do I opt out?</span></span>

<span data-ttu-id="5d265-144">今後の変更をオプトアウトするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5d265-144">To opt out of the upcoming change, complete these steps:</span></span>

1. <span data-ttu-id="5d265-145">組織でグローバル管理者のアクセス許可を持つ仕事または学校のアカウントを使用して、Windows PowerShellセッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="5d265-145">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="5d265-146">手順については、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d265-146">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="5d265-147">次の構文Set-IRMConfigurationを使用して、このコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="5d265-147">Run the Set-IRMConfiguration cmdlet using the following syntax:</span></span>

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a><span data-ttu-id="5d265-148">この変更が行われた後、何を期待できますか?</span><span class="sxs-lookup"><span data-stu-id="5d265-148">What can I expect after this change has been made?</span></span>

<span data-ttu-id="5d265-149">これを有効にした後、オプトアウトしていない場合は [、Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) で発表された新しいバージョンの Office 365 Message Encryption の使用を開始し、Azure Information Protection の暗号化と保護機能を活用できます。</span><span class="sxs-lookup"><span data-stu-id="5d265-149">Once this is enabled, provided you haven't opted out, you can start using the new version of Office 365 Message Encryption which was announced at [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) and leverages the encryption and protection capabilities of Azure Information Protection.</span></span>

![Outlook on the web で OME で保護されたメッセージを示すスクリーンショット。](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

<span data-ttu-id="5d265-151">新しい拡張機能の詳細については [、「365 message Encryption Officeを参照してください](../../compliance/ome.md)。</span><span class="sxs-lookup"><span data-stu-id="5d265-151">For more information about the new enhancements, see [Office 365 Message Encryption](../../compliance/ome.md).</span></span>