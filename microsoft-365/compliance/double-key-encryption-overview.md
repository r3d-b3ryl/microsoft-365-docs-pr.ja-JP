---
title: ダブル キー暗号化の概要と FAQ
description: Microsoft 365 のダブル キー暗号化に関するよく寄せられる質問。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 12/11/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: ed07361f8c433a318342ae3c8ad750549992c285
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922051"
---
# <a name="double-key-encryption-frequently-asked-questions"></a><span data-ttu-id="7b3e3-103">二重キー暗号化に関するよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="7b3e3-103">Double Key Encryption frequently asked questions</span></span>

<span data-ttu-id="7b3e3-104">ダブル キー暗号化の仕組みについて質問がありますか?</span><span class="sxs-lookup"><span data-stu-id="7b3e3-104">Have a question about how Double Key Encryption works?</span></span> <span data-ttu-id="7b3e3-105">ここで答えを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-105">Check for an answer here.</span></span>

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a><span data-ttu-id="7b3e3-106">Microsoft 365 (DKE) のダブル キー暗号化とは</span><span class="sxs-lookup"><span data-stu-id="7b3e3-106">What is Double Key Encryption for Microsoft 365 (DKE)?</span></span>

<span data-ttu-id="7b3e3-107">Microsoft 365 のダブル キー暗号化を使用すると、お客様は機密性の高いデータを保護して、特別な要件を満たします。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-107">Double Key Encryption for Microsoft 365 enables customers to protect their highly sensitive data to meet specialized requirements.</span></span> <span data-ttu-id="7b3e3-108">これにより、お客様は暗号化キーの完全な制御を維持できます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-108">It helps customers maintain full control of their encryption keys.</span></span> <span data-ttu-id="7b3e3-109">2 つのキーを使用してデータを保護します。コントロール内の 1 つのキーと、Microsoft Azure に安全に格納された 2 番目のキー。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-109">It uses two keys to protect data; one key in your control and a second key stored securely in Microsoft Azure.</span></span> <span data-ttu-id="7b3e3-110">ダブル キー暗号化で保護されたデータを表示するには、両方のキーにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-110">Viewing data protected with Double Key Encryption requires access to both keys.</span></span> <span data-ttu-id="7b3e3-111">Microsoft ではこれらのキーの 1 つしかアクセスできないので、保護されたデータは Microsoft にアクセスできなくなり、データのプライバシーとセキュリティを完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-111">Since Microsoft can access only one of these keys, protected data remains inaccessible to Microsoft, ensuring that you have full control over your data privacy and security.</span></span>  

<span data-ttu-id="7b3e3-112">選択した場所 (オンプレミスのキー管理サーバーまたはクラウド内) で、キーを要求するために使用する Double Key Encryption サービスをホストできます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-112">You can host the Double Key Encryption service used to request your key, in a location of your choice (on-premises key management server or in the cloud).</span></span> <span data-ttu-id="7b3e3-113">他のアプリケーションと同じ方法でサービスを維持します。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-113">You maintain the service as you would any other application.</span></span> <span data-ttu-id="7b3e3-114">ダブル キー暗号化を使用すると、ダブル キー暗号化サービスへのアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-114">Double Key Encryption enables you to control access to the Double Key Encryption service.</span></span> <span data-ttu-id="7b3e3-115">機密性の高いデータは、オンプレミスに保存するか、クラウドに移動できます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-115">You can store your highly sensitive data on-premises or move it to the cloud.</span></span> <span data-ttu-id="7b3e3-116">キーの完全な制御を維持するために、サード パーティ製のアクセスを防ぐことに自信を持って取り組む必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-116">You can be confident about preventing third-party access because you maintain full control of your key.</span></span> <span data-ttu-id="7b3e3-117">ダブル キー暗号化を使用すると、データとキーを同じ場所に格納できます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-117">Double Key Encryption allows you to store your data and key in the same location.</span></span>

<span data-ttu-id="7b3e3-118">DKE は、一般データ保護規則 (GDPR)、健康保険の移植性および説明責任法 (HIPAA)、Gramm-Leach-Bliley 法 (GLBA)、ロシアのデータローカライズ法 - 連邦法番号など、いくつかの規制および基準に関する規制要件を満たすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-118">DKE helps you meet regulatory requirements across several regulations and standards such as the General Data Protection Regulation (GDPR), the Health Insurance Portability and Accountability Act (HIPAA), the Gramm-Leach-Bliley Act (GLBA), Russia’s data localization law – Federal Law No.</span></span> <span data-ttu-id="7b3e3-119">242-FZ、オーストラリアの連邦プライバシー法 1988、およびニュージーランドのプライバシー法 1993。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-119">242-FZ, Australia’s Federal Privacy Act 1988, and New Zealand’s Privacy Act 1993.</span></span>

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a><span data-ttu-id="7b3e3-120">組み込みの感度ラベル付Microsoft Officeキー暗号化を使用できますか?</span><span class="sxs-lookup"><span data-stu-id="7b3e3-120">Can I use Double Key Encryption with Microsoft Office built-in sensitivity labeling?</span></span>

<span data-ttu-id="7b3e3-121">Azure Information Protection 統合ラベル付けクライアントを使用して、ダブル キー暗号化を使用してドキュメントを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-121">You'll need to use the Azure Information Protection unified labeling client to protect documents with Double Key Encryption.</span></span> <span data-ttu-id="7b3e3-122">現在、組み込みのMicrosoft Officeラベルを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-122">Currently, you can't use Microsoft Office built-in sensitivity labeling.</span></span>

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a><span data-ttu-id="7b3e3-123">DKE で使用できる Microsoft 365 アプリ</span><span class="sxs-lookup"><span data-stu-id="7b3e3-123">What Microsoft 365 Apps can I use with DKE?</span></span>

<span data-ttu-id="7b3e3-124">Windows のデスクトップ バージョンの Word、Excel、および PowerPoint を使用して、DKE ラベルを使用してドキュメントを保護できます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-124">You can use DKE labels to protect documents using the desktop versions of Word, Excel, and PowerPoint on Windows.</span></span> <span data-ttu-id="7b3e3-125">Windows で \*.12711 以降 (デスクトップ バージョンの Word、PowerPoint、Excel) を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-125">Ensure that you're using \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a><span data-ttu-id="7b3e3-126">ダブル キー暗号化と既存のホールド 独自のキー (HYOK) ソリューションの違い</span><span class="sxs-lookup"><span data-stu-id="7b3e3-126">How is Double Key Encryption different from the existing hold your own key (HYOK) solution?</span></span>

<span data-ttu-id="7b3e3-127">ダブル キー暗号化は、2 つのキーを使用してデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-127">Double Key Encryption encrypts your data with two keys.</span></span> <span data-ttu-id="7b3e3-128">暗号化キーはコントロールに格納され、2 番目のキーは Microsoft Azure に保存され、暗号化されたデータをクラウドに移動できます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-128">Your encryption key is in your control and the second key is stored in Microsoft Azure, allowing you to move your encrypted data to the cloud.</span></span> <span data-ttu-id="7b3e3-129">HYOK は 1 つのキーでのみコンテンツを保護し、キーは常にオンプレミスにあります。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-129">HYOK protects your content with only one key and the key is always on premises.</span></span>  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a><span data-ttu-id="7b3e3-130">Double Key Encrypted documents を外部で共有できますか?</span><span class="sxs-lookup"><span data-stu-id="7b3e3-130">Can Double Key Encrypted documents be shared externally?</span></span>

<span data-ttu-id="7b3e3-131">Double Key Encrypted documents は、次のユーザーである限り、別のテナントのユーザーと共有できます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-131">You can share Double Key Encrypted documents with users on a separate tenant as long as those users:</span></span>

- <span data-ttu-id="7b3e3-132">ダブル キー暗号化サービスでキーにアクセスするために必要なアクセス許可を持つ。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-132">Have the required permission to access your key in your Double Key Encryption service.</span></span>

- <span data-ttu-id="7b3e3-133">Microsoft Azure でキーにアクセスするために必要なアクセス許可を持っている。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-133">Have the required permission to access your key in Microsoft Azure.</span></span>

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a><span data-ttu-id="7b3e3-134">HYOK で保護されているドキュメントは何が起こりますか?</span><span class="sxs-lookup"><span data-stu-id="7b3e3-134">What happens to documents that are protected with HYOK?</span></span>

<span data-ttu-id="7b3e3-135">ダブル キー暗号化を展開しても、既存の HYOK セットアップには影響しません。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-135">Deploying Double Key Encryption won't affect your existing HYOK setup.</span></span> <span data-ttu-id="7b3e3-136">ただし、HYOK と並行してダブル キー暗号化の使用を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-136">However, we recommend that you start using Double Key Encryption in parallel with HYOK.</span></span>

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a><span data-ttu-id="7b3e3-137">Microsoft 以外の空きモード環境でダブル キー暗号化を実行できますか?</span><span class="sxs-lookup"><span data-stu-id="7b3e3-137">Can I run Double Key Encryption in my non-Microsoft air-gapped environment?</span></span>

<span data-ttu-id="7b3e3-138">DKE は、サービスが Microsoft Azure へのアクセスを必要とするために、これらの環境をサポートしません。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-138">DKE doesn't support these environments because the service requires access to Microsoft Azure.</span></span>

## <a name="where-can-i-store-double-key-encrypted-documents"></a><span data-ttu-id="7b3e3-139">Double Key Encrypted ドキュメントはどこに保存できますか?</span><span class="sxs-lookup"><span data-stu-id="7b3e3-139">Where can I store Double Key Encrypted documents?</span></span>

<span data-ttu-id="7b3e3-140">Double Key Encrypted ドキュメントは、オンプレミスまたはクラウドに保存できます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-140">You can store Double Key Encrypted documents on-premises or in the cloud.</span></span> <span data-ttu-id="7b3e3-141">クラウドでは、暗号化されたコンテンツを SharePoint Online および OneDrive for Business に移動できます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-141">In the cloud, you can move encrypted content to SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="7b3e3-142">Microsoft はプライベート キーにアクセスできないので、暗号化されたデータは Microsoft に対して不透明なままです。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-142">Since Microsoft doesn't have access to your private key, the encrypted data remains opaque to Microsoft.</span></span> <span data-ttu-id="7b3e3-143">つまり、暗号化されたドキュメントを Web Apps でオンラインOffice表示できません。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-143">This also means that you can't view the encrypted documents online in Office Web Apps.</span></span>

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a><span data-ttu-id="7b3e3-144">利用可能な二重キー暗号化とは、どの地域と言語ですか?</span><span class="sxs-lookup"><span data-stu-id="7b3e3-144">What regions and languages is Double Key Encryption available in?</span></span> <span data-ttu-id="7b3e3-145">ダブル キー暗号化は世界中で利用できますか?</span><span class="sxs-lookup"><span data-stu-id="7b3e3-145">Is Double Key Encryption available worldwide?</span></span>

<span data-ttu-id="7b3e3-146">DKE ラベルは、Microsoft Information Protection の他の感度ラベルと同じ言語にローカライズされます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-146">DKE labels are localized to the same languages as other sensitivity labels in Microsoft Information Protection.</span></span> <span data-ttu-id="7b3e3-147">ダブル キー暗号化は世界中で利用できます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-147">Double Key Encryption is available worldwide.</span></span>

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a><span data-ttu-id="7b3e3-148">DKE 以外のラベルを DKE ラベルに変換できますか?</span><span class="sxs-lookup"><span data-stu-id="7b3e3-148">Can I convert a non-DKE label to a DKE label?</span></span>

<span data-ttu-id="7b3e3-149">いいえ。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-149">No.</span></span> <span data-ttu-id="7b3e3-150">ラベルを作成した後は、DKE をラベルに追加できない。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-150">You can’t add DKE to a label after you create it.</span></span> <span data-ttu-id="7b3e3-151">代わりに、[ダブル キー暗号化を **使用する** ] を選択し、ラベルを作成するときに、ダブル キー暗号化サービスの URL を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-151">Instead, you must choose **Use Double Key Encryption** and provide the URL of your Double Key Encryption service when you create the label.</span></span>

## <a name="how-do-i-roll-my-dke-keys"></a><span data-ttu-id="7b3e3-152">DKE キーをロールする方法</span><span class="sxs-lookup"><span data-stu-id="7b3e3-152">How do I roll my DKE keys?</span></span>

<span data-ttu-id="7b3e3-153">Azure に格納するキーのローリング (回転またはキー変更とも呼ばれる) の手順については [、「Operations for your Azure Information Protection テナント](/azure/information-protection/operations-customer-managed-tenant-key)キー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-153">For instructions on rolling (also called rotating or rekeying) the key you store in Azure, see [Operations for your Azure Information Protection tenant key](/azure/information-protection/operations-customer-managed-tenant-key).</span></span>

<span data-ttu-id="7b3e3-154">DKE [サービスの新しいキーの](double-key-encryption.md#tenant-and-key-settings) 作成については、「テナントとキーの設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-154">See [Tenant and key settings](double-key-encryption.md#tenant-and-key-settings) for information on creating a new key for the DKE service.</span></span>

<span data-ttu-id="7b3e3-155">キーを作成するときに、名前と GUID を設定します。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-155">When you create a key, you set up a name and a GUID.</span></span> <span data-ttu-id="7b3e3-156">次に、キーを回転する場合は、名前と GUID を持つ古いレコードを保持しますが、同じ名前で GUID が異なる新しいレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-156">Then, if you rotate a key, you keep the old record with the name and GUID but add a new record with the same name but different GUID.</span></span> <span data-ttu-id="7b3e3-157">新しいキーがアクティブとして設定され、公開キー API が新しい暗号化のために返しを開始します。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-157">The new key gets set as active so that the public key API starts returning it for new encryption.</span></span> <span data-ttu-id="7b3e3-158">両方のキーを復号化して、新しいコンテンツと古いコンテンツを復号化できます。</span><span class="sxs-lookup"><span data-stu-id="7b3e3-158">Both keys are available for decryption so that new content and old content can be decrypted.</span></span>