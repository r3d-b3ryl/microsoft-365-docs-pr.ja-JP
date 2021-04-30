---
title: データ損失防止ポリシーヒントのリファレンス
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
recommendations: false
description: データ損失防止 (DLP) ポリシーにポリシー ヒントを追加する方法について、DLP ポリシーと競合するコンテンツを操作しているユーザーに通知する方法について学習します。
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 0c42569da3fcac40d3121a59f7dc004f25dd3f74
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086761"
---
# <a name="data-loss-prevention-policy-tips-reference"></a><span data-ttu-id="84002-103">データ損失防止ポリシーヒントのリファレンス</span><span class="sxs-lookup"><span data-stu-id="84002-103">Data Loss Prevention policy tips reference</span></span>

<span data-ttu-id="84002-104">Outlook Web Access の DLP ポリシー ヒントは、以下を除き、DLP ポリシー内の Exchange ワークロードに適用可能なすべての条件、例外、およびアクションでサポートされます。</span><span class="sxs-lookup"><span data-stu-id="84002-104">DLP policy tips in Outlook Web Access is supported for all the conditions, exceptions and actions that are applicable on Exchange workload in a DLP policy except the following:</span></span>

<span data-ttu-id="84002-105">**条件:**</span><span class="sxs-lookup"><span data-stu-id="84002-105">**Conditions:**</span></span>

- <span data-ttu-id="84002-106">Sender Is</span><span class="sxs-lookup"><span data-stu-id="84002-106">Sender Is</span></span>
- <span data-ttu-id="84002-107">Sender Domain Is</span><span class="sxs-lookup"><span data-stu-id="84002-107">Sender Domain Is</span></span>
- <span data-ttu-id="84002-108">受信者は、</span><span class="sxs-lookup"><span data-stu-id="84002-108">Recipient is a member of</span></span>
- <span data-ttu-id="84002-109">ヘッダーには、単語または語句が含まれています</span><span class="sxs-lookup"><span data-stu-id="84002-109">Header contains words or phrases</span></span>
- <span data-ttu-id="84002-110">ヘッダーがパターンと一致する</span><span class="sxs-lookup"><span data-stu-id="84002-110">Header matches patterns</span></span>
- <span data-ttu-id="84002-111">ドキュメント のサイズが等しいか、またはより大きい</span><span class="sxs-lookup"><span data-stu-id="84002-111">Document size equals or is greater than</span></span>
- <span data-ttu-id="84002-112">メッセージの種類は次の値です。</span><span class="sxs-lookup"><span data-stu-id="84002-112">Message type is</span></span>
- <span data-ttu-id="84002-113">メッセージの重要度は、</span><span class="sxs-lookup"><span data-stu-id="84002-113">Message importance is</span></span>
- <span data-ttu-id="84002-114">コンテンツ文字セットに単語が含まれている</span><span class="sxs-lookup"><span data-stu-id="84002-114">Content character set contains words</span></span>
- <span data-ttu-id="84002-115">件名または本文に単語または語句が含まれる</span><span class="sxs-lookup"><span data-stu-id="84002-115">Subject or body contains words or phrases</span></span>
- <span data-ttu-id="84002-116">件名または本文がパターンと一致する</span><span class="sxs-lookup"><span data-stu-id="84002-116">Subject or body matches patterns</span></span>
- <span data-ttu-id="84002-117">コンテンツ文字セットに単語が含まれている</span><span class="sxs-lookup"><span data-stu-id="84002-117">Content character set contains words</span></span>
- <span data-ttu-id="84002-118">コンテンツの受信</span><span class="sxs-lookup"><span data-stu-id="84002-118">Content is received from</span></span>
- <span data-ttu-id="84002-119">送信者がポリシー ヒントを上書きしました</span><span class="sxs-lookup"><span data-stu-id="84002-119">Has sender overridden the policy tip</span></span>
- <span data-ttu-id="84002-120">メッセージ サイズが等しいか、またはより大きい</span><span class="sxs-lookup"><span data-stu-id="84002-120">Message size equals or is greater than</span></span>
- <span data-ttu-id="84002-121">Sender AD属性に単語または語句が含まれている</span><span class="sxs-lookup"><span data-stu-id="84002-121">Sender AD attribute contains words or phrases</span></span>
- <span data-ttu-id="84002-122">Sender AD属性がパターンと一致する</span><span class="sxs-lookup"><span data-stu-id="84002-122">Sender AD attribute matches patterns</span></span>
- <span data-ttu-id="84002-123">ドキュメントコンテンツには、単語または語句が含まれる</span><span class="sxs-lookup"><span data-stu-id="84002-123">Document content contains words or phrases</span></span>
- <span data-ttu-id="84002-124">ドキュメント コンテンツがパターンと一致する</span><span class="sxs-lookup"><span data-stu-id="84002-124">Document content matches patterns</span></span>

<span data-ttu-id="84002-125">**アクション:**</span><span class="sxs-lookup"><span data-stu-id="84002-125">**Actions:**</span></span>

- <span data-ttu-id="84002-126">承認のためにメッセージを送信者のマネージャーに転送する</span><span class="sxs-lookup"><span data-stu-id="84002-126">Forward the message for approval to sender’s manager</span></span>
- <span data-ttu-id="84002-127">承認のメッセージを特定の承認者に転送する</span><span class="sxs-lookup"><span data-stu-id="84002-127">Forward the message for approval to specific approvers</span></span>
- <span data-ttu-id="84002-128">メッセージを特定のユーザーにリダイレクトする</span><span class="sxs-lookup"><span data-stu-id="84002-128">Redirect the message to specific users</span></span>
- <span data-ttu-id="84002-129">宛先ボックスに受信者を追加する</span><span class="sxs-lookup"><span data-stu-id="84002-129">Add recipients to the To Box</span></span>
- <span data-ttu-id="84002-130">Cc ボックスに受信者を追加する</span><span class="sxs-lookup"><span data-stu-id="84002-130">Add recipients to the Cc Box</span></span>
- <span data-ttu-id="84002-131">Bcc ボックスに受信者を追加する</span><span class="sxs-lookup"><span data-stu-id="84002-131">Add recipients to the Bcc Box</span></span>
- <span data-ttu-id="84002-132">送信者のマネージャーを受信者として追加する</span><span class="sxs-lookup"><span data-stu-id="84002-132">Add the sender’s manager as recipient</span></span>
- <span data-ttu-id="84002-133">HTML 免責事項の追加</span><span class="sxs-lookup"><span data-stu-id="84002-133">Add HTML disclaimer</span></span>
- <span data-ttu-id="84002-134">電子メールの件名の先頭に追加する</span><span class="sxs-lookup"><span data-stu-id="84002-134">Prepend email subject</span></span>
- <span data-ttu-id="84002-135">O365 メッセージの暗号化と権限の保護を削除する</span><span class="sxs-lookup"><span data-stu-id="84002-135">Remove O365 Message Encryption and rights protection</span></span>

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a><span data-ttu-id="84002-136">Outlook 2013 以降では、一部の条件と例外に関するポリシー ヒントの表示がサポートされています</span><span class="sxs-lookup"><span data-stu-id="84002-136">Outlook 2013 and later supports showing policy tips for only some conditions and exceptions</span></span>

<span data-ttu-id="84002-137">現在、Outlook 2013 以降では、以下の条件と対応する例外以外の条件や例外を含むポリシーに関するポリシー ヒントの表示がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="84002-137">Currently, Outlook 2013 and later supports showing policy tips for policies which do not contain any condition or exception apart from the below mentioned conditions and corresponding exceptions :</span></span>

- <span data-ttu-id="84002-138">コンテンツが含まれる (機密情報の種類に対してのみ機能します)。</span><span class="sxs-lookup"><span data-stu-id="84002-138">Content contains (works only for Sensitive information types.</span></span> <span data-ttu-id="84002-139">感度ラベルはサポートされていません)</span><span class="sxs-lookup"><span data-stu-id="84002-139">Sensitivity labels are not supported)</span></span>
- <span data-ttu-id="84002-140">コンテンツが共有されている</span><span class="sxs-lookup"><span data-stu-id="84002-140">Content is shared</span></span>

<span data-ttu-id="84002-141">すべての条件は、コンテンツと一致し、コンテンツに対して保護アクションを適用Outlookクライアント アプリで作成された電子メールに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="84002-141">Note that all the conditions work for emails authored in Outlook client app, where they will match content and enforce protective actions on content.</span></span> <span data-ttu-id="84002-142">ただし、ユーザーにポリシー ヒントを表示する方法は、上記の条件とは別に使用される条件ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="84002-142">However, showing policy tips to users is not supported for any conditions that are used apart from the ones mentioned above.</span></span>

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="84002-143">Outlook 2013 以降およびデスクトップ上Officeアプリの一部の機密情報の種類についてのみポリシー ヒントを表示するサポート</span><span class="sxs-lookup"><span data-stu-id="84002-143">Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types</span></span>

<span data-ttu-id="84002-144">デスクトップ上の Outlook (2013 以降) および Office アプリ (Word、Excel、PowerPoint) で DLP ポリシー ヒントをデスクトップに表示するために検出される、既定の機密情報の種類の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="84002-144">The list of out-of-the-box sensitive information types that will be detected for showing DLP policy tips in Outlook on Desktop (2013 and later) and Office apps (Word, Excel, PowerPoint) on Desktop are the following :</span></span>

- <span data-ttu-id="84002-145">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="84002-145">ABA Routing Number</span></span>
- <span data-ttu-id="84002-146">アルゼンチンの国民識別 (DNI) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-146">Argentina National Identity (DNI) Number</span></span>
- <span data-ttu-id="84002-147">オーストラリアの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="84002-147">Australia Bank Account Number</span></span>
- <span data-ttu-id="84002-148">オーストラリアの医療口座番号</span><span class="sxs-lookup"><span data-stu-id="84002-148">Australia Medical Account Number</span></span>
- <span data-ttu-id="84002-149">オーストラリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-149">Australia Passport Number</span></span>
- <span data-ttu-id="84002-150">オーストラリアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="84002-150">Australia Tax File Number</span></span>
- <span data-ttu-id="84002-151">Azure DocumentDB Auth Key</span><span class="sxs-lookup"><span data-stu-id="84002-151">Azure DocumentDB Auth Key</span></span>  
- <span data-ttu-id="84002-152">Azure IAAS データベース接続文字列と Azure SQL接続文字列</span><span class="sxs-lookup"><span data-stu-id="84002-152">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>  
- <span data-ttu-id="84002-153">Azure IoT接続文字列</span><span class="sxs-lookup"><span data-stu-id="84002-153">Azure IoT Connection String</span></span>  
- <span data-ttu-id="84002-154">Azure 発行設定パスワード</span><span class="sxs-lookup"><span data-stu-id="84002-154">Azure Publish Setting Password</span></span>  
- <span data-ttu-id="84002-155">Azure Redis キャッシュ接続文字列</span><span class="sxs-lookup"><span data-stu-id="84002-155">Azure Redis Cache Connection String</span></span>  
- <span data-ttu-id="84002-156">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="84002-156">Azure SAS</span></span>  
- <span data-ttu-id="84002-157">Azure Service Bus接続文字列</span><span class="sxs-lookup"><span data-stu-id="84002-157">Azure Service Bus Connection String</span></span>  
- <span data-ttu-id="84002-158">Azure Storageアカウント キー</span><span class="sxs-lookup"><span data-stu-id="84002-158">Azure Storage Account Key</span></span>  
- <span data-ttu-id="84002-159">Azure Storageアカウント キー (汎用)</span><span class="sxs-lookup"><span data-stu-id="84002-159">Azure Storage Account Key (Generic)</span></span>  
- <span data-ttu-id="84002-160">ベルギーの国民番号</span><span class="sxs-lookup"><span data-stu-id="84002-160">Belgium National Number</span></span>
- <span data-ttu-id="84002-161">ブラジルの CPF 番号</span><span class="sxs-lookup"><span data-stu-id="84002-161">Brazil CPF Number</span></span>
- <span data-ttu-id="84002-162">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="84002-162">Brazil Legal Entity Number (CNPJ)</span></span>
- <span data-ttu-id="84002-163">	ブラジルの国民識別カード (RG)</span><span class="sxs-lookup"><span data-stu-id="84002-163">Brazil National ID Card (RG)</span></span>
- <span data-ttu-id="84002-164">カナダの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="84002-164">Canada Bank Account Number</span></span>
- <span data-ttu-id="84002-165">カナダの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-165">Canada Driver's License Number</span></span>
- <span data-ttu-id="84002-166">カナダの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="84002-166">Canada Health Service Number</span></span>
- <span data-ttu-id="84002-167">カナダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-167">Canada Passport Number</span></span>
- <span data-ttu-id="84002-168">カナダの個人保健識別番号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="84002-168">Canada Personal Health Identification Number (PHIN)</span></span>
- <span data-ttu-id="84002-169">カナダの社会保険番号</span><span class="sxs-lookup"><span data-stu-id="84002-169">Canada Social Insurance Number</span></span>
- <span data-ttu-id="84002-170">	チリの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="84002-170">Chile Identity Card Number</span></span>
- <span data-ttu-id="84002-171">	中国の居民身分証明書 (PRC) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-171">China Resident Identity Card (PRC) Number</span></span>
- <span data-ttu-id="84002-172">クレジット カード番号</span><span class="sxs-lookup"><span data-stu-id="84002-172">Credit Card Number</span></span>
- <span data-ttu-id="84002-173">クロアチアの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="84002-173">Croatia Identity Card Number</span></span>  
- <span data-ttu-id="84002-174">クロアチアの個人識別 (OIB) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-174">Croatia Personal Identification (OIB) Number</span></span>  
- <span data-ttu-id="84002-175">チェコの個人 ID 番号</span><span class="sxs-lookup"><span data-stu-id="84002-175">Czech Personal Identity Number</span></span>  
- <span data-ttu-id="84002-176">デンマークの個人識別番号</span><span class="sxs-lookup"><span data-stu-id="84002-176">Denmark Personal Identification Number</span></span>
- <span data-ttu-id="84002-177">麻薬取締局 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-177">Drug Enforcement Agency (DEA) Number</span></span>
- <span data-ttu-id="84002-178">欧州連合のデビット カード番号</span><span class="sxs-lookup"><span data-stu-id="84002-178">EU Debit Card Number</span></span>
- <span data-ttu-id="84002-179">EU の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-179">EU Driver's License Number</span></span>  
- <span data-ttu-id="84002-180">EU の国民識別番号</span><span class="sxs-lookup"><span data-stu-id="84002-180">EU National Identification Number</span></span>  
- <span data-ttu-id="84002-181">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-181">EU Passport Number</span></span>  
- <span data-ttu-id="84002-182">EU 社会保障番号 (SSN) または同等の ID</span><span class="sxs-lookup"><span data-stu-id="84002-182">EU Social Security Number (SSN) or Equivalent ID</span></span>  
- <span data-ttu-id="84002-183">EU 税 ID 番号 (TIN)</span><span class="sxs-lookup"><span data-stu-id="84002-183">EU Tax Identification Number (TIN)</span></span>  
- <span data-ttu-id="84002-184">フィンランドの国民 ID</span><span class="sxs-lookup"><span data-stu-id="84002-184">Finland National ID</span></span>
- <span data-ttu-id="84002-185">フィンランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-185">Finland Passport Number</span></span>
- <span data-ttu-id="84002-186">フランスの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-186">France Driver's License Number</span></span>
- <span data-ttu-id="84002-187">フランスの国民識別カード (CNI)</span><span class="sxs-lookup"><span data-stu-id="84002-187">France National ID Card (CNI)</span></span>
- <span data-ttu-id="84002-188">フランスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-188">France Passport Number</span></span>
- <span data-ttu-id="84002-189">フランスの社会保障番号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="84002-189">France Social Security Number (INSEE)</span></span>
- <span data-ttu-id="84002-190">ドイツの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-190">German Driver's License Number</span></span>
- <span data-ttu-id="84002-191">ドイツのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-191">German Passport Number</span></span>
- <span data-ttu-id="84002-192">ドイツの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="84002-192">Germany Identity Card Number</span></span>
- <span data-ttu-id="84002-193">ギリシャの国民識別カード</span><span class="sxs-lookup"><span data-stu-id="84002-193">Greece National ID Card</span></span>  
- <span data-ttu-id="84002-194">香港の ID カード (HKID) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-194">Hong Kong Identity Card (HKID) Number</span></span>
- <span data-ttu-id="84002-195">インドの永久口座番号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="84002-195">India Permanent Account Number (PAN)</span></span>
- <span data-ttu-id="84002-196">インドの固有識別 (Aadhaar) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-196">India Unique Identification (Aadhaar) Number</span></span>
- <span data-ttu-id="84002-197">インドネシアの身分証明書 (KTP) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-197">Indonesia Identity Card (KTP) Number</span></span>
- <span data-ttu-id="84002-198">国際銀行口座番号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="84002-198">International Banking Account Number (IBAN)</span></span>
- <span data-ttu-id="84002-199">国際分類の病気 (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="84002-199">International Classification of Diseases (ICD-10-CM)</span></span>  
- <span data-ttu-id="84002-200">国際疾病分類 (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="84002-200">International Classification of Diseases (ICD-9-CM)</span></span>  
- <span data-ttu-id="84002-201">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="84002-201">IP Address</span></span>
- <span data-ttu-id="84002-202">アイルランドの個人公共サービス (PPS) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-202">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="84002-203">イスラエルの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="84002-203">Israel Bank Account Number</span></span>
- <span data-ttu-id="84002-204">イスラエルの国民 ID</span><span class="sxs-lookup"><span data-stu-id="84002-204">Israel National ID</span></span>
- <span data-ttu-id="84002-205">イタリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-205">Italy Driver's License Number</span></span>
- <span data-ttu-id="84002-206">日本の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="84002-206">Japan Bank Account Number</span></span>
- <span data-ttu-id="84002-207">日本の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-207">Japan Driver's License Number</span></span>
- <span data-ttu-id="84002-208">日本のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-208">Japan Passport Number</span></span>
- <span data-ttu-id="84002-209">日本の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="84002-209">Japan Resident Registration Number</span></span>
- <span data-ttu-id="84002-210">日本の社会保険番号 (SIN)</span><span class="sxs-lookup"><span data-stu-id="84002-210">Japan Social Insurance Number (SIN)</span></span>
- <span data-ttu-id="84002-211">日本の在留カード番号</span><span class="sxs-lookup"><span data-stu-id="84002-211">Japanese Residence Card Number</span></span>
- <span data-ttu-id="84002-212">マレーシアの ID カード番号</span><span class="sxs-lookup"><span data-stu-id="84002-212">Malaysia Identity Card Number</span></span>
- <span data-ttu-id="84002-213">オランダの市民サービス (BSN) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-213">Netherlands Citizen's Service (BSN) Number</span></span>  
- <span data-ttu-id="84002-214">ニュージーランドの保健省番号</span><span class="sxs-lookup"><span data-stu-id="84002-214">New Zealand Ministry of Health Number</span></span>
- <span data-ttu-id="84002-215">ノルウェーの識別番号</span><span class="sxs-lookup"><span data-stu-id="84002-215">Norway Identity Number</span></span>  
- <span data-ttu-id="84002-216">フィリピンの汎用多目的 ID 番号</span><span class="sxs-lookup"><span data-stu-id="84002-216">Philippines Unified Multi-Purpose ID Number</span></span>
- <span data-ttu-id="84002-217">ポーランドの ID カード</span><span class="sxs-lookup"><span data-stu-id="84002-217">Poland Identity Card</span></span>
- <span data-ttu-id="84002-218">ポーランドの国民 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="84002-218">Poland National ID (PESEL)</span></span>
- <span data-ttu-id="84002-219">ポーランドのパスポート</span><span class="sxs-lookup"><span data-stu-id="84002-219">Poland Passport</span></span>
- <span data-ttu-id="84002-220">ポルトガルの市民カード番号</span><span class="sxs-lookup"><span data-stu-id="84002-220">Portugal Citizen Card Number</span></span>
- <span data-ttu-id="84002-221">サウジアラビアの国民 ID</span><span class="sxs-lookup"><span data-stu-id="84002-221">Saudi Arabia National ID</span></span>
- <span data-ttu-id="84002-222">シンガポールの国民登録 ID カード (NRIC) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-222">Singapore National Registration Identity Card (NRIC) Number</span></span>
- <span data-ttu-id="84002-223">南アフリカの識別番号</span><span class="sxs-lookup"><span data-stu-id="84002-223">South Africa Identification Number</span></span>  
- <span data-ttu-id="84002-224">韓国の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="84002-224">South Korea Resident Registration Number</span></span>
- <span data-ttu-id="84002-225">スペインの社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="84002-225">Spain Social Security Number (SSN)</span></span>
- <span data-ttu-id="84002-226">SQL Server接続文字列</span><span class="sxs-lookup"><span data-stu-id="84002-226">SQL Server Connection String</span></span>  
- <span data-ttu-id="84002-227">スウェーデンの国民 ID</span><span class="sxs-lookup"><span data-stu-id="84002-227">Sweden National ID</span></span>
- <span data-ttu-id="84002-228">スウェーデンのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-228">Sweden Passport Number</span></span>
- <span data-ttu-id="84002-229">SWIFT コード</span><span class="sxs-lookup"><span data-stu-id="84002-229">SWIFT Code</span></span>
- <span data-ttu-id="84002-230">台湾の国民 ID</span><span class="sxs-lookup"><span data-stu-id="84002-230">Taiwan National ID</span></span>
- <span data-ttu-id="84002-231">	台湾のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-231">Taiwan Passport Number</span></span>
- <span data-ttu-id="84002-232">台湾居住者証明書 (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="84002-232">Taiwan Resident Certificate (ARC/TARC)</span></span>
- <span data-ttu-id="84002-233">タイの人口識別コード</span><span class="sxs-lookup"><span data-stu-id="84002-233">Thai Population Identification Code</span></span>
- <span data-ttu-id="84002-234">トルコの国民識別番号</span><span class="sxs-lookup"><span data-stu-id="84002-234">Turkish National Identification number</span></span>
- <span data-ttu-id="84002-p103">英国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-p103">U.K. Driver's License Number</span></span>
- <span data-ttu-id="84002-p104">英国の選挙登録番号</span><span class="sxs-lookup"><span data-stu-id="84002-p104">U.K. Electoral Roll Number</span></span>
- <span data-ttu-id="84002-p105">英国の国民健康保険番号</span><span class="sxs-lookup"><span data-stu-id="84002-p105">U.K. National Health Service Number</span></span>
- <span data-ttu-id="84002-p106">英国の国民保険番号 (NINO)</span><span class="sxs-lookup"><span data-stu-id="84002-p106">U.K. National Insurance Number (NINO)</span></span>
- <span data-ttu-id="84002-p107">米国/英国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-p107">U.S. / U.K. Passport Number</span></span>
- <span data-ttu-id="84002-245">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="84002-245">U.S. Bank Account Number</span></span>
- <span data-ttu-id="84002-246">米国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-246">U.S. Driver's License Number</span></span>
- <span data-ttu-id="84002-247">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="84002-247">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="84002-248">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="84002-248">U.S. Social Security Number (SSN)</span></span>

<span data-ttu-id="84002-249">カスタムの機密情報の種類は、上記の機密情報の種類に加えて、DLP ポリシー のヒントにもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="84002-249">Please note that custom sensitive information types are also supported for DLP policy tips in addition to the above out-of-the-box sensitive information types.</span></span>

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a><span data-ttu-id="84002-250">エンドポイント デバイスのデータ損失防止は、一部の機密情報の種類についてのみポリシー ヒントをサポートします</span><span class="sxs-lookup"><span data-stu-id="84002-250">Data Loss Prevention on endpoint devices supports policy tips for only some sensitive information types</span></span>

<span data-ttu-id="84002-251">エンドポイント デバイスに存在するドキュメントで検出される、既定の機密情報の種類の一覧は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="84002-251">The list of out-of-the-box sensitive information types that will be detected in documents residing on endpoint devices are the following :</span></span>

- <span data-ttu-id="84002-252">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="84002-252">ABA Routing Number</span></span> 
- <span data-ttu-id="84002-253">アルゼンチンの国民識別 (DNI) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-253">Argentina National Identity (DNI) Number</span></span> 
- <span data-ttu-id="84002-254">オーストラリアの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="84002-254">Australia Bank Account Number</span></span> 
- <span data-ttu-id="84002-255">オーストラリアの医療口座番号</span><span class="sxs-lookup"><span data-stu-id="84002-255">Australia Medical Account Number</span></span> 
- <span data-ttu-id="84002-256">オーストラリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-256">Australia Passport Number</span></span> 
- <span data-ttu-id="84002-257">オーストラリアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="84002-257">Australia Tax File Number</span></span> 
- <span data-ttu-id="84002-258">オーストラリアのビジネス番号</span><span class="sxs-lookup"><span data-stu-id="84002-258">Australian Business Number</span></span> 
- <span data-ttu-id="84002-259">オーストラリアの会社番号</span><span class="sxs-lookup"><span data-stu-id="84002-259">Australian Company Number</span></span> 
- <span data-ttu-id="84002-260">オーストリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-260">Austria Driver's License Number</span></span> 
- <span data-ttu-id="84002-261">オーストリアの ID カード</span><span class="sxs-lookup"><span data-stu-id="84002-261">Austria Identity Card</span></span> 
- <span data-ttu-id="84002-262">オーストリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-262">Austria Passport Number</span></span> 
- <span data-ttu-id="84002-263">オーストリアの社会保障番号</span><span class="sxs-lookup"><span data-stu-id="84002-263">Austria Social Security Number</span></span> 
- <span data-ttu-id="84002-264">オーストリアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="84002-264">Austria Tax Identification Number</span></span> 
- <span data-ttu-id="84002-265">オーストリア付加価値税 (VAT) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-265">Austria Value Added Tax (VAT) Number</span></span> 
- <span data-ttu-id="84002-266">Azure DocumentDB Auth Key</span><span class="sxs-lookup"><span data-stu-id="84002-266">Azure DocumentDB Auth Key</span></span> 
- <span data-ttu-id="84002-267">Azure IAAS データベース接続文字列と Azure SQL接続文字列</span><span class="sxs-lookup"><span data-stu-id="84002-267">Azure IAAS Database Connection String and Azure SQL Connection String</span></span> 
- <span data-ttu-id="84002-268">Azure IoT接続文字列</span><span class="sxs-lookup"><span data-stu-id="84002-268">Azure IoT Connection String</span></span> 
- <span data-ttu-id="84002-269">Azure 発行設定パスワード</span><span class="sxs-lookup"><span data-stu-id="84002-269">Azure Publish Setting Password</span></span> 
- <span data-ttu-id="84002-270">Azure Redis キャッシュ接続文字列</span><span class="sxs-lookup"><span data-stu-id="84002-270">Azure Redis Cache Connection String</span></span> 
- <span data-ttu-id="84002-271">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="84002-271">Azure SAS</span></span> 
- <span data-ttu-id="84002-272">Azure Service Bus接続文字列</span><span class="sxs-lookup"><span data-stu-id="84002-272">Azure Service Bus Connection String</span></span> 
- <span data-ttu-id="84002-273">Azure Storageアカウント キー</span><span class="sxs-lookup"><span data-stu-id="84002-273">Azure Storage Account Key</span></span> 
- <span data-ttu-id="84002-274">Azure Storageアカウント キー (汎用)</span><span class="sxs-lookup"><span data-stu-id="84002-274">Azure Storage Account Key (Generic)</span></span> 
- <span data-ttu-id="84002-275">ベルギーの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-275">Belgium Driver's License Number</span></span> 
- <span data-ttu-id="84002-276">ベルギーの国民番号</span><span class="sxs-lookup"><span data-stu-id="84002-276">Belgium National Number</span></span> 
- <span data-ttu-id="84002-277">ベルギーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-277">Belgium Passport Number</span></span> 
- <span data-ttu-id="84002-278">ベルギーの付加価値税番号</span><span class="sxs-lookup"><span data-stu-id="84002-278">Belgium Value Added Tax Number</span></span> 
- <span data-ttu-id="84002-279">ブラジルの CPF 番号</span><span class="sxs-lookup"><span data-stu-id="84002-279">Brazil CPF Number</span></span> 
- <span data-ttu-id="84002-280">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="84002-280">Brazil Legal Entity Number (CNPJ)</span></span> 
- <span data-ttu-id="84002-281">	ブラジルの国民識別カード (RG)</span><span class="sxs-lookup"><span data-stu-id="84002-281">Brazil National ID Card (RG)</span></span> 
- <span data-ttu-id="84002-282">ブルガリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-282">Bulgaria Driver's License Number</span></span> 
- <span data-ttu-id="84002-283">ブルガリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-283">Bulgaria Passport Number</span></span> 
- <span data-ttu-id="84002-284">ブルガリアの統一市民番号</span><span class="sxs-lookup"><span data-stu-id="84002-284">Bulgaria Uniform Civil Number</span></span> 
- <span data-ttu-id="84002-285">カナダの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="84002-285">Canada Bank Account Number</span></span> 
- <span data-ttu-id="84002-286">カナダの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-286">Canada Driver's License Number</span></span> 
- <span data-ttu-id="84002-287">カナダの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="84002-287">Canada Health Service Number</span></span> 
- <span data-ttu-id="84002-288">カナダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-288">Canada Passport Number</span></span> 
- <span data-ttu-id="84002-289">カナダの個人保健識別番号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="84002-289">Canada Personal Health Identification Number (PHIN)</span></span> 
- <span data-ttu-id="84002-290">カナダの社会保険番号</span><span class="sxs-lookup"><span data-stu-id="84002-290">Canada Social Insurance Number</span></span> 
- <span data-ttu-id="84002-291">	チリの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="84002-291">Chile Identity Card Number</span></span> 
- <span data-ttu-id="84002-292">	中国の居民身分証明書 (PRC) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-292">China Resident Identity Card (PRC) Number</span></span> 
- <span data-ttu-id="84002-293">クレジットカード番号</span><span class="sxs-lookup"><span data-stu-id="84002-293">Credit Card Number</span></span> 
- <span data-ttu-id="84002-294">クロアチア の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-294">Croatia Driver's License Number</span></span> 
- <span data-ttu-id="84002-295">クロアチアの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="84002-295">Croatia Identity Card Number</span></span> 
- <span data-ttu-id="84002-296">クロアチアの国民 ID カード番号</span><span class="sxs-lookup"><span data-stu-id="84002-296">Croatia National ID Card Number</span></span> 
- <span data-ttu-id="84002-297">クロアチアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-297">Croatia Passport Number</span></span> 
- <span data-ttu-id="84002-298">クロアチアの個人識別 (OIB) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-298">Croatia Personal Identification (OIB) Number</span></span> 
- <span data-ttu-id="84002-299">CSCAN-AZURE0060 Azure Storage共有アクセス署名</span><span class="sxs-lookup"><span data-stu-id="84002-299">CSCAN-AZURE0060 Azure Storage Account Shared Access Signature</span></span> 
- <span data-ttu-id="84002-300">CSCAN-GENERAL0140 一般対称キー</span><span class="sxs-lookup"><span data-stu-id="84002-300">CSCAN-GENERAL0140 General Symmetric Key</span></span> 
- <span data-ttu-id="84002-301">キプロス の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-301">Cyprus Driver's License Number</span></span> 
- <span data-ttu-id="84002-302">キプロスの ID カード</span><span class="sxs-lookup"><span data-stu-id="84002-302">Cyprus Identity Card</span></span> 
- <span data-ttu-id="84002-303">キプロスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-303">Cyprus Passport Number</span></span> 
- <span data-ttu-id="84002-304">キプロスの納税者番号</span><span class="sxs-lookup"><span data-stu-id="84002-304">Cyprus Tax Identification Number</span></span> 
- <span data-ttu-id="84002-305">チェコの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-305">Czech Driver's License Number</span></span> 
- <span data-ttu-id="84002-306">チェコの個人 ID 番号</span><span class="sxs-lookup"><span data-stu-id="84002-306">Czech Personal Identity Number</span></span> 
- <span data-ttu-id="84002-307">チェコ共和国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-307">Czech Republic Passport Number</span></span> 
- <span data-ttu-id="84002-308">デンマークの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-308">Denmark Driver's License Number</span></span> 
- <span data-ttu-id="84002-309">デンマークのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-309">Denmark Passport Number</span></span> 
- <span data-ttu-id="84002-310">デンマークの個人識別番号</span><span class="sxs-lookup"><span data-stu-id="84002-310">Denmark Personal Identification Number</span></span> 
- <span data-ttu-id="84002-311">麻薬取締局 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-311">Drug Enforcement Agency (DEA) Number</span></span> 
- <span data-ttu-id="84002-312">エストニア の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-312">Estonia Driver's License Number</span></span> 
- <span data-ttu-id="84002-313">エストニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-313">Estonia Passport Number</span></span> 
- <span data-ttu-id="84002-314">エストニアの個人識別コード</span><span class="sxs-lookup"><span data-stu-id="84002-314">Estonia Personal Identification Code</span></span> 
- <span data-ttu-id="84002-315">欧州連合のデビット カード番号</span><span class="sxs-lookup"><span data-stu-id="84002-315">EU Debit Card Number</span></span> 
- <span data-ttu-id="84002-316">EU の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-316">EU Driver's License Number</span></span> 
- <span data-ttu-id="84002-317">EU の国民識別番号</span><span class="sxs-lookup"><span data-stu-id="84002-317">EU National Identification Number</span></span> 
- <span data-ttu-id="84002-318">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-318">EU Passport Number</span></span> 
- <span data-ttu-id="84002-319">EU 社会保障番号 (SSN) または同等の ID</span><span class="sxs-lookup"><span data-stu-id="84002-319">EU Social Security Number (SSN) or Equivalent ID</span></span> 
- <span data-ttu-id="84002-320">EU 税 ID 番号 (TIN)</span><span class="sxs-lookup"><span data-stu-id="84002-320">EU Tax Identification Number (TIN)</span></span> 
- <span data-ttu-id="84002-321">フィンランド の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-321">Finland Driver's License Number</span></span> 
- <span data-ttu-id="84002-322">フィンランド のヨーロッパの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="84002-322">Finland European Health Insurance Number</span></span> 
- <span data-ttu-id="84002-323">フィンランドの国民 ID</span><span class="sxs-lookup"><span data-stu-id="84002-323">Finland National ID</span></span> 
- <span data-ttu-id="84002-324">フィンランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-324">Finland Passport Number</span></span> 
- <span data-ttu-id="84002-325">フランスの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-325">France Driver's License Number</span></span> 
- <span data-ttu-id="84002-326">フランスの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="84002-326">France Health Insurance Number</span></span> 
- <span data-ttu-id="84002-327">フランスの国民識別カード (CNI)</span><span class="sxs-lookup"><span data-stu-id="84002-327">France National ID Card (CNI)</span></span> 
- <span data-ttu-id="84002-328">フランスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-328">France Passport Number</span></span> 
- <span data-ttu-id="84002-329">フランスの社会保障番号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="84002-329">France Social Security Number (INSEE)</span></span> 
- <span data-ttu-id="84002-330">フランスの納税者番号 (numéro SPI.)</span><span class="sxs-lookup"><span data-stu-id="84002-330">France Tax Identification Number (numéro SPI.)</span></span> 
- <span data-ttu-id="84002-331">フランスの付加価値税番号</span><span class="sxs-lookup"><span data-stu-id="84002-331">France Value Added Tax Number</span></span> 
- <span data-ttu-id="84002-332">ドイツの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-332">German Driver's License Number</span></span> 
- <span data-ttu-id="84002-333">ドイツのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-333">German Passport Number</span></span> 
- <span data-ttu-id="84002-334">ドイツの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="84002-334">Germany Identity Card Number</span></span> 
- <span data-ttu-id="84002-335">ドイツの納税者番号</span><span class="sxs-lookup"><span data-stu-id="84002-335">Germany Tax Identification Number</span></span> 
- <span data-ttu-id="84002-336">ドイツの付加価値税番号</span><span class="sxs-lookup"><span data-stu-id="84002-336">Germany Value Added Tax Number</span></span> 
- <span data-ttu-id="84002-337">ギリシャの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-337">Greece Driver's License Number</span></span> 
- <span data-ttu-id="84002-338">ギリシャの国民識別カード</span><span class="sxs-lookup"><span data-stu-id="84002-338">Greece National ID Card</span></span> 
- <span data-ttu-id="84002-339">ギリシャのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-339">Greece Passport Number</span></span> 
- <span data-ttu-id="84002-340">ギリシャの社会保障番号 (AMKA)</span><span class="sxs-lookup"><span data-stu-id="84002-340">Greece Social Security Number (AMKA)</span></span> 
- <span data-ttu-id="84002-341">ギリシャ語の税の識別番号</span><span class="sxs-lookup"><span data-stu-id="84002-341">Greek Tax identification Number</span></span> 
- <span data-ttu-id="84002-342">香港の ID カード (HKID) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-342">Hong Kong Identity Card (HKID) Number</span></span> 
- <span data-ttu-id="84002-343">ハンガリーの社会保障番号 (TAJ)</span><span class="sxs-lookup"><span data-stu-id="84002-343">Hungarian Social Security Number (TAJ)</span></span> 
- <span data-ttu-id="84002-344">ハンガリーの付加価値税番号</span><span class="sxs-lookup"><span data-stu-id="84002-344">Hungarian Value Added Tax Number</span></span> 
- <span data-ttu-id="84002-345">ハンガリー の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-345">Hungary Driver's License Number</span></span> 
- <span data-ttu-id="84002-346">ハンガリーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-346">Hungary Passport Number</span></span> 
- <span data-ttu-id="84002-347">ハンガリーの個人識別番号</span><span class="sxs-lookup"><span data-stu-id="84002-347">Hungary Personal Identification Number</span></span> 
- <span data-ttu-id="84002-348">ハンガリー 税の識別番号</span><span class="sxs-lookup"><span data-stu-id="84002-348">Hungary Tax identification Number</span></span> 
- <span data-ttu-id="84002-349">インドの永久口座番号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="84002-349">India Permanent Account Number (PAN)</span></span> 
- <span data-ttu-id="84002-350">インドの固有識別 (Aadhaar) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-350">India Unique Identification (Aadhaar) Number</span></span> 
- <span data-ttu-id="84002-351">インドネシアの身分証明書 (KTP) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-351">Indonesia Identity Card (KTP) Number</span></span> 
- <span data-ttu-id="84002-352">国際銀行口座番号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="84002-352">International Banking Account Number (IBAN)</span></span> 
- <span data-ttu-id="84002-353">国際分類の病気 (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="84002-353">International Classification of Diseases (ICD-10-CM)</span></span> 
- <span data-ttu-id="84002-354">国際疾病分類 (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="84002-354">International Classification of Diseases (ICD-9-CM)</span></span> 
- <span data-ttu-id="84002-355">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="84002-355">IP Address</span></span> 
- <span data-ttu-id="84002-356">アイルランドの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-356">Ireland Driver's License Number</span></span> 
- <span data-ttu-id="84002-357">アイルランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-357">Ireland Passport Number</span></span> 
- <span data-ttu-id="84002-358">アイルランドの個人公共サービス (PPS) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-358">Ireland Personal Public Service (PPS) Number</span></span> 
- <span data-ttu-id="84002-359">イスラエルの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="84002-359">Israel Bank Account Number</span></span> 
- <span data-ttu-id="84002-360">イスラエルの国民 ID</span><span class="sxs-lookup"><span data-stu-id="84002-360">Israel National ID</span></span> 
- <span data-ttu-id="84002-361">イタリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-361">Italy Driver's License Number</span></span> 
- <span data-ttu-id="84002-362">イタリアの会計コード</span><span class="sxs-lookup"><span data-stu-id="84002-362">Italy Fiscal Code</span></span> 
- <span data-ttu-id="84002-363">イタリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-363">Italy Passport Number</span></span> 
- <span data-ttu-id="84002-364">イタリアの付加価値税番号</span><span class="sxs-lookup"><span data-stu-id="84002-364">Italy Value Added Tax Number</span></span> 
- <span data-ttu-id="84002-365">日本の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="84002-365">Japan Bank Account Number</span></span> 
- <span data-ttu-id="84002-366">日本の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-366">Japan Driver's License Number</span></span> 
- <span data-ttu-id="84002-367">日本のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-367">Japan Passport Number</span></span> 
- <span data-ttu-id="84002-368">日本の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="84002-368">Japan Resident Registration Number</span></span> 
- <span data-ttu-id="84002-369">日本の社会保険番号 (SIN)</span><span class="sxs-lookup"><span data-stu-id="84002-369">Japan Social Insurance Number (SIN)</span></span> 
- <span data-ttu-id="84002-370">日本語 My Number Corporate</span><span class="sxs-lookup"><span data-stu-id="84002-370">Japanese My Number Corporate</span></span> 
- <span data-ttu-id="84002-371">日本語の個人用番号</span><span class="sxs-lookup"><span data-stu-id="84002-371">Japanese My Number Personal</span></span> 
- <span data-ttu-id="84002-372">日本の在留カード番号</span><span class="sxs-lookup"><span data-stu-id="84002-372">Japanese Residence Card Number</span></span> 
- <span data-ttu-id="84002-373">ラトビア の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-373">Latvia Driver's License Number</span></span> 
- <span data-ttu-id="84002-374">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-374">Latvia Passport Number</span></span> 
- <span data-ttu-id="84002-375">ラトビアの個人コード</span><span class="sxs-lookup"><span data-stu-id="84002-375">Latvia Personal Code</span></span> 
- <span data-ttu-id="84002-376">リトアニア の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-376">Lithuania Driver's License Number</span></span> 
- <span data-ttu-id="84002-377">リトアニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-377">Lithuania Passport Number</span></span> 
- <span data-ttu-id="84002-378">リトアニア の個人用コード</span><span class="sxs-lookup"><span data-stu-id="84002-378">Lithuania Personal Code</span></span> 
- <span data-ttu-id="84002-379">ルクセンブルク 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-379">Luxemburg Driver's License Number</span></span> 
- <span data-ttu-id="84002-380">ルクセンブルク国民識別番号 (自然人)</span><span class="sxs-lookup"><span data-stu-id="84002-380">Luxemburg National Identification Number (Natural persons)</span></span> 
- <span data-ttu-id="84002-381">ルクセンブルク国民識別番号 (非自然人)</span><span class="sxs-lookup"><span data-stu-id="84002-381">Luxemburg National Identification Number (Non-natural persons)</span></span> 
- <span data-ttu-id="84002-382">ルクセンブルク パスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-382">Luxemburg Passport Number</span></span> 
- <span data-ttu-id="84002-383">マレーシアの ID カード番号</span><span class="sxs-lookup"><span data-stu-id="84002-383">Malaysia Identity Card Number</span></span> 
- <span data-ttu-id="84002-384">マルタの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-384">Malta Driver's License Number</span></span> 
- <span data-ttu-id="84002-385">マルタの ID カード番号</span><span class="sxs-lookup"><span data-stu-id="84002-385">Malta Identity Card Number</span></span> 
- <span data-ttu-id="84002-386">マルタのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-386">Malta Passport Number</span></span> 
- <span data-ttu-id="84002-387">マルタ税 ID 番号</span><span class="sxs-lookup"><span data-stu-id="84002-387">Malta Tax ID Number</span></span> 
- <span data-ttu-id="84002-388">オランダの市民サービス (BSN) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-388">Netherlands Citizen's Service (BSN) Number</span></span> 
- <span data-ttu-id="84002-389">オランダの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-389">Netherlands Driver's License Number</span></span> 
- <span data-ttu-id="84002-390">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-390">Netherlands Passport Number</span></span> 
- <span data-ttu-id="84002-391">オランダの納税者番号</span><span class="sxs-lookup"><span data-stu-id="84002-391">Netherlands Tax Identification Number</span></span> 
- <span data-ttu-id="84002-392">オランダの付加価値税番号</span><span class="sxs-lookup"><span data-stu-id="84002-392">Netherlands Value Added Tax Number</span></span> 
- <span data-ttu-id="84002-393">ニュージーランドの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="84002-393">New Zealand bank account number</span></span> 
- <span data-ttu-id="84002-394">ニュージーランドの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-394">New Zealand Driver License Number</span></span> 
- <span data-ttu-id="84002-395">ニュージーランド 内陸の収益番号</span><span class="sxs-lookup"><span data-stu-id="84002-395">New Zealand Inland Revenue number</span></span> 
- <span data-ttu-id="84002-396">ニュージーランドの保健省番号</span><span class="sxs-lookup"><span data-stu-id="84002-396">New Zealand Ministry of Health Number</span></span> 
- <span data-ttu-id="84002-397">ニュージーランドのソーシャル 福利厚生番号</span><span class="sxs-lookup"><span data-stu-id="84002-397">New Zealand Social Welfare Number</span></span> 
- <span data-ttu-id="84002-398">ノルウェーの識別番号</span><span class="sxs-lookup"><span data-stu-id="84002-398">Norway Identity Number</span></span> 
- <span data-ttu-id="84002-399">フィリピンの汎用多目的 ID 番号</span><span class="sxs-lookup"><span data-stu-id="84002-399">Philippines Unified Multi-Purpose ID Number</span></span> 
- <span data-ttu-id="84002-400">ポーランド の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-400">Poland Driver's License Number</span></span> 
- <span data-ttu-id="84002-401">ポーランドの ID カード</span><span class="sxs-lookup"><span data-stu-id="84002-401">Poland Identity Card</span></span> 
- <span data-ttu-id="84002-402">ポーランドの国民 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="84002-402">Poland National ID (PESEL)</span></span> 
- <span data-ttu-id="84002-403">ポーランドのパスポート</span><span class="sxs-lookup"><span data-stu-id="84002-403">Poland Passport</span></span> 
- <span data-ttu-id="84002-404">ポーランドの納税者番号</span><span class="sxs-lookup"><span data-stu-id="84002-404">Poland Tax Identification Number</span></span> 
- <span data-ttu-id="84002-405">ポーランド語 REGON 番号</span><span class="sxs-lookup"><span data-stu-id="84002-405">Polish REGON Number</span></span> 
- <span data-ttu-id="84002-406">ポルトガルの市民カード番号</span><span class="sxs-lookup"><span data-stu-id="84002-406">Portugal Citizen Card Number</span></span> 
- <span data-ttu-id="84002-407">ポルトガルの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-407">Portugal Driver's License Number</span></span> 
- <span data-ttu-id="84002-408">ポルトガルのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-408">Portugal Passport Number</span></span> 
- <span data-ttu-id="84002-409">ポルトガルの納税者番号</span><span class="sxs-lookup"><span data-stu-id="84002-409">Portugal Tax Identification Number</span></span> 
- <span data-ttu-id="84002-410">ルーマニアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-410">Romania Driver's License Number</span></span> 
- <span data-ttu-id="84002-411">ルーマニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-411">Romania Passport Number</span></span> 
- <span data-ttu-id="84002-412">ルーマニア の個人数値コード (CNP)</span><span class="sxs-lookup"><span data-stu-id="84002-412">Romania Personal Numerical Code (CNP)</span></span> 
- <span data-ttu-id="84002-413">ロシアのパスポート番号 (国内)</span><span class="sxs-lookup"><span data-stu-id="84002-413">Russian Passport Number (Domestic)</span></span> 
- <span data-ttu-id="84002-414">ロシアのパスポート番号 (国際)</span><span class="sxs-lookup"><span data-stu-id="84002-414">Russian Passport Number (International)</span></span> 
- <span data-ttu-id="84002-415">サウジアラビアの国民 ID</span><span class="sxs-lookup"><span data-stu-id="84002-415">Saudi Arabia National ID</span></span> 
- <span data-ttu-id="84002-416">シンガポールの国民登録 ID カード (NRIC) 番号</span><span class="sxs-lookup"><span data-stu-id="84002-416">Singapore National Registration Identity Card (NRIC) Number</span></span> 
- <span data-ttu-id="84002-417">スロバキアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-417">Slovakia Driver's License Number</span></span> 
- <span data-ttu-id="84002-418">スロバキアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-418">Slovakia Passport Number</span></span> 
- <span data-ttu-id="84002-419">スロバキアの個人番号</span><span class="sxs-lookup"><span data-stu-id="84002-419">Slovakia Personal Number</span></span> 
- <span data-ttu-id="84002-420">スロベニア の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-420">Slovenia Driver's License Number</span></span> 
- <span data-ttu-id="84002-421">スロベニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-421">Slovenia Passport Number</span></span> 
- <span data-ttu-id="84002-422">スロベニアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="84002-422">Slovenia Tax Identification Number</span></span> 
- <span data-ttu-id="84002-423">スロベニアの一意のマスター市民番号</span><span class="sxs-lookup"><span data-stu-id="84002-423">Slovenia Unique Master Citizen Number</span></span> 
- <span data-ttu-id="84002-424">南アフリカの識別番号</span><span class="sxs-lookup"><span data-stu-id="84002-424">South Africa Identification Number</span></span> 
- <span data-ttu-id="84002-425">韓国の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="84002-425">South Korea Resident Registration Number</span></span> 
- <span data-ttu-id="84002-426">スペイン DNI</span><span class="sxs-lookup"><span data-stu-id="84002-426">Spain DNI</span></span> 
- <span data-ttu-id="84002-427">スペインの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-427">Spain Driver's License Number</span></span> 
- <span data-ttu-id="84002-428">スペインのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-428">Spain Passport Number</span></span> 
- <span data-ttu-id="84002-429">スペインの社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="84002-429">Spain Social Security Number (SSN)</span></span> 
- <span data-ttu-id="84002-430">スペインの納税者番号</span><span class="sxs-lookup"><span data-stu-id="84002-430">Spain Tax Identification Number</span></span> 
- <span data-ttu-id="84002-431">SQL Server接続文字列</span><span class="sxs-lookup"><span data-stu-id="84002-431">SQL Server Connection String</span></span> 
- <span data-ttu-id="84002-432">スウェーデンの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-432">Sweden Driver's License Number</span></span> 
- <span data-ttu-id="84002-433">スウェーデンの国民 ID</span><span class="sxs-lookup"><span data-stu-id="84002-433">Sweden National ID</span></span> 
- <span data-ttu-id="84002-434">スウェーデンのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-434">Sweden Passport Number</span></span> 
- <span data-ttu-id="84002-435">スウェーデンの納税者番号</span><span class="sxs-lookup"><span data-stu-id="84002-435">Sweden Tax Identification Number</span></span> 
- <span data-ttu-id="84002-436">SWIFT コード</span><span class="sxs-lookup"><span data-stu-id="84002-436">SWIFT Code</span></span> 
- <span data-ttu-id="84002-437">スイスの社会保障番号 AHV</span><span class="sxs-lookup"><span data-stu-id="84002-437">Swiss Social Security Number AHV</span></span> 
- <span data-ttu-id="84002-438">台湾の国民 ID</span><span class="sxs-lookup"><span data-stu-id="84002-438">Taiwan National ID</span></span> 
- <span data-ttu-id="84002-439">	台湾のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-439">Taiwan Passport Number</span></span> 
- <span data-ttu-id="84002-440">台湾居住者証明書 (ARC/TARC)</span><span class="sxs-lookup"><span data-stu-id="84002-440">Taiwan Resident Certificate (ARC/TARC)</span></span> 
- <span data-ttu-id="84002-441">タイの人口識別コード</span><span class="sxs-lookup"><span data-stu-id="84002-441">Thai Population Identification Code</span></span> 
- <span data-ttu-id="84002-442">トルコの国民識別番号</span><span class="sxs-lookup"><span data-stu-id="84002-442">Turkish National Identification number</span></span> 
- <span data-ttu-id="84002-p108">英国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-p108">U.K. Driver's License Number</span></span> 
- <span data-ttu-id="84002-p109">英国の選挙登録番号</span><span class="sxs-lookup"><span data-stu-id="84002-p109">U.K. Electoral Roll Number</span></span> 
- <span data-ttu-id="84002-p110">英国の国民健康保険番号</span><span class="sxs-lookup"><span data-stu-id="84002-p110">U.K. National Health Service Number</span></span> 
- <span data-ttu-id="84002-p111">英国の国民保険番号 (NINO)</span><span class="sxs-lookup"><span data-stu-id="84002-p111">U.K. National Insurance Number (NINO)</span></span> 
- <span data-ttu-id="84002-451">英国</span><span class="sxs-lookup"><span data-stu-id="84002-451">U.K.</span></span> <span data-ttu-id="84002-452">一意の納税者参照番号</span><span class="sxs-lookup"><span data-stu-id="84002-452">Unique Taxpayer Reference Number</span></span> 
- <span data-ttu-id="84002-p113">米国/英国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="84002-p113">U.S. / U.K. Passport Number</span></span> 
- <span data-ttu-id="84002-455">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="84002-455">U.S. Bank Account Number</span></span> 
- <span data-ttu-id="84002-456">米国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="84002-456">U.S. Driver's License Number</span></span> 
- <span data-ttu-id="84002-457">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="84002-457">U.S. Individual Taxpayer Identification Number (ITIN)</span></span> 
- <span data-ttu-id="84002-458">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="84002-458">U.S. Social Security Number (SSN)</span></span> 
- <span data-ttu-id="84002-459">ウクライナのパスポート番号 (国内)</span><span class="sxs-lookup"><span data-stu-id="84002-459">Ukraine Passport Number (Domestic)</span></span> 
- <span data-ttu-id="84002-460">ウクライナのパスポート番号 (国際)</span><span class="sxs-lookup"><span data-stu-id="84002-460">Ukraine Passport Number (International)</span></span> 
 
<span data-ttu-id="84002-461">上記の機密情報の種類に加えて、カスタムの機密情報の種類も検出されます。</span><span class="sxs-lookup"><span data-stu-id="84002-461">Please note that custom sensitive information types will also be detected in addition to the above out-of-the-box sensitive information types</span></span>

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a><span data-ttu-id="84002-462">Microsoft アプリ全体の DLP ポリシー ヒントのサポート マトリックス</span><span class="sxs-lookup"><span data-stu-id="84002-462">Support Matrix for DLP policy tips across Microsoft apps</span></span>

|<span data-ttu-id="84002-463">**アプリとプラットフォーム**</span><span class="sxs-lookup"><span data-stu-id="84002-463">**App and platform**</span></span>|<span data-ttu-id="84002-464">**DLP ポリシー ヒントのサポート**</span><span class="sxs-lookup"><span data-stu-id="84002-464">**DLP policy tip support**</span></span>|<span data-ttu-id="84002-465">**サポートされる機密情報の種類**</span><span class="sxs-lookup"><span data-stu-id="84002-465">**Sensitive information types supported**</span></span>|<span data-ttu-id="84002-466">**サポートされる述語とアクション**</span><span class="sxs-lookup"><span data-stu-id="84002-466">**Predicates and actions supported**</span></span>|<span data-ttu-id="84002-467">**コメント**</span><span class="sxs-lookup"><span data-stu-id="84002-467">**Comments**</span></span>|
|:--|:--|:--|:--|:--|
|<span data-ttu-id="84002-468">**OutlookWeb アクセス**</span><span class="sxs-lookup"><span data-stu-id="84002-468">**Outlook Web Access**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="84002-469">すべて</span><span class="sxs-lookup"><span data-stu-id="84002-469">All</span></span>|<span data-ttu-id="84002-470">Subset</span><span class="sxs-lookup"><span data-stu-id="84002-470">Subset</span></span>|<span data-ttu-id="84002-471">「 [データ損失防止ポリシー のヒントリファレンス」を参照してください。](#data-loss-prevention-policy-tips-reference)</span><span class="sxs-lookup"><span data-stu-id="84002-471">See [Data Loss Prevention policy tips reference](#data-loss-prevention-policy-tips-reference)</span></span>|
|<span data-ttu-id="84002-472">**OutlookWin32 (Outlook 2013 以降)**</span><span class="sxs-lookup"><span data-stu-id="84002-472">**Outlook Win32 (Outlook 2013 and beyond)**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="84002-473">Subset</span><span class="sxs-lookup"><span data-stu-id="84002-473">Subset</span></span>|<span data-ttu-id="84002-474">Subset</span><span class="sxs-lookup"><span data-stu-id="84002-474">Subset</span></span>|<span data-ttu-id="84002-475">Outlook Win32 での DLP ポリシー ヒントの表示にサポートされる機密情報の種類と DLP の条件とアクションのサポートの詳細については[、「Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions)以降では、一部の条件と例外に関するポリシー ヒントの表示と[Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types)以降およびデスクトップ上の Office アプリのサポート」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84002-475">See [Outlook 2013 and later supports showing policy tips for only some conditions and exceptions](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) and [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for details on support for sensitive information types and DLP conditions and actions supported for showing DLP policy tips on Outlook Win32.</span></span>|
|<span data-ttu-id="84002-476">**Outlookモバイル (iOS、Android)/Outlook Mac**</span><span class="sxs-lookup"><span data-stu-id="84002-476">**Outlook Mobile (iOS, Android)/Outlook Mac**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="84002-477">なし</span><span class="sxs-lookup"><span data-stu-id="84002-477">None</span></span>|<span data-ttu-id="84002-478">なし</span><span class="sxs-lookup"><span data-stu-id="84002-478">None</span></span>|<span data-ttu-id="84002-479">DLP ポリシー のヒントは、モバイルではOutlookされません</span><span class="sxs-lookup"><span data-stu-id="84002-479">DLP policy tips are not supported on Outlook mobile</span></span>|
|<span data-ttu-id="84002-480">**Sharepoint Online/One Drive for Business Web クライアント**</span><span class="sxs-lookup"><span data-stu-id="84002-480">**Sharepoint Online/One Drive for Business Web client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="84002-481">すべて</span><span class="sxs-lookup"><span data-stu-id="84002-481">All</span></span>|<span data-ttu-id="84002-482">DLP のすべての SPO/ODB 述語とアクション</span><span class="sxs-lookup"><span data-stu-id="84002-482">All SPO/ODB predicates and actions in DLP</span></span>||
|<span data-ttu-id="84002-483">**Sharepoint Win32/ One Drive for Business Win32 クライアント**</span><span class="sxs-lookup"><span data-stu-id="84002-483">**Sharepoint Win32/ One Drive for Business Win32 client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="84002-484">なし</span><span class="sxs-lookup"><span data-stu-id="84002-484">None</span></span>|<span data-ttu-id="84002-485">なし</span><span class="sxs-lookup"><span data-stu-id="84002-485">None</span></span>|<span data-ttu-id="84002-486">SHAREpoint またはデスクトップ クライアント アプリでは DLP ポリシーのヒントOneDriveサポートされていません</span><span class="sxs-lookup"><span data-stu-id="84002-486">DLP policy tips are not supported on Sharepoint or OneDrive desktop client apps</span></span>|
|<span data-ttu-id="84002-487">**Word、Excel、PowerPoint Web クライアント**</span><span class="sxs-lookup"><span data-stu-id="84002-487">**Word, Excel, PowerPoint Web Client**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="84002-488">すべて</span><span class="sxs-lookup"><span data-stu-id="84002-488">All</span></span>|<span data-ttu-id="84002-489">DLP のすべての SPO/ODB 述語とアクション</span><span class="sxs-lookup"><span data-stu-id="84002-489">All SPO/ODB predicates and actions in DLP</span></span>|<span data-ttu-id="84002-490">DLP ポリシー ヒントは、ドキュメントが SPO または ODB Web アプリでホストされ、DLP ポリシーが既にスタンプされている場合にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="84002-490">DLP policy tip is supported if the document is hosted on SPO or ODB web app and the DLP policy is already stamped.</span></span>|
|<span data-ttu-id="84002-491">**Word、Excel、PowerPoint Mobile クライアント**</span><span class="sxs-lookup"><span data-stu-id="84002-491">**Word, Excel, PowerPoint Mobile Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="84002-492">なし</span><span class="sxs-lookup"><span data-stu-id="84002-492">None</span></span>|<span data-ttu-id="84002-493">なし</span><span class="sxs-lookup"><span data-stu-id="84002-493">None</span></span>|<span data-ttu-id="84002-494">DLP ポリシー のヒントは、モバイル アプリではサポートされていません。Office。</span><span class="sxs-lookup"><span data-stu-id="84002-494">DLP policy tips are not supported in mobile apps for Office.</span></span>|
|<span data-ttu-id="84002-495">**TeamsWeb/ Teams デスクトップ/ Teams Mobile/ Teams Mac**</span><span class="sxs-lookup"><span data-stu-id="84002-495">**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="84002-496">すべて</span><span class="sxs-lookup"><span data-stu-id="84002-496">All</span></span>|<span data-ttu-id="84002-497">DLP ポリシー Teams述語のすべて</span><span class="sxs-lookup"><span data-stu-id="84002-497">All Teams predicates in DLP policy</span></span>|<span data-ttu-id="84002-498">ポリシー ヒントは、メッセージに "このメッセージのフラグが設定されています" というフラグが付けらた場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="84002-498">Policy tips will show when a message is flagged as “This message has been flagged.</span></span> <span data-ttu-id="84002-499">何が可能ですか?</span><span class="sxs-lookup"><span data-stu-id="84002-499">What can I do?”</span></span> <span data-ttu-id="84002-500">リンクをクリックすると、ユーザーは検出された機密情報の種類を確認し、管理者が許可した場合に問題を上書きまたは報告できます。ファイルに関するポリシー ヒントは表示されません。</span><span class="sxs-lookup"><span data-stu-id="84002-500">When clicking the link, the user can review the sensitive info types detected and override or report an issue if allowed by the admin. Note that no policy tips are shown for files.</span></span> <span data-ttu-id="84002-501">受信者がドキュメントにアクセスしようとすると、許可されていない場合にアクセスが拒否される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="84002-501">When the recipient tries to access the document, they might get access denied if not allowed.</span></span>|
|<span data-ttu-id="84002-502">**Win32 Endpoint Devices**</span><span class="sxs-lookup"><span data-stu-id="84002-502">**Win32 Endpoint Devices**</span></span>|:::image type="icon" source="../media/rightmrk.png" border="false":::|<span data-ttu-id="84002-503">Subset</span><span class="sxs-lookup"><span data-stu-id="84002-503">Subset</span></span>|<span data-ttu-id="84002-504">DLP ポリシーのすべてのエンドポイント DLP 述語とアクション</span><span class="sxs-lookup"><span data-stu-id="84002-504">All Endpoint DLP predicates and actions in DLP policy</span></span>|<span data-ttu-id="84002-505">「 [エンドポイントのデータ損失防止は、一部の機密情報の種類についてのみポリシー ヒントをサポートしています」を参照してください。](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span><span class="sxs-lookup"><span data-stu-id="84002-505">See [Data Loss Prevention on Endpoint supports policy tips for only some sensitive information types](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types)</span></span>|
|<span data-ttu-id="84002-506">**Mac デバイス**</span><span class="sxs-lookup"><span data-stu-id="84002-506">**Mac devices**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="84002-507">なし</span><span class="sxs-lookup"><span data-stu-id="84002-507">None</span></span>|<span data-ttu-id="84002-508">なし</span><span class="sxs-lookup"><span data-stu-id="84002-508">None</span></span>|<span data-ttu-id="84002-509">データ損失防止ポリシーは、今日の Mac デバイスでは適用できません</span><span class="sxs-lookup"><span data-stu-id="84002-509">Data loss prevention policies are not enforceable on Mac devices today</span></span>|
|<span data-ttu-id="84002-510">**サードパーティのクラウド アプリ**</span><span class="sxs-lookup"><span data-stu-id="84002-510">**3rd party cloud apps**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="84002-511">なし</span><span class="sxs-lookup"><span data-stu-id="84002-511">None</span></span>|<span data-ttu-id="84002-512">なし</span><span class="sxs-lookup"><span data-stu-id="84002-512">None</span></span>|<span data-ttu-id="84002-513">データ損失防止ポリシーのヒントは、サードパーティのクラウド アプリではサポートされていません</span><span class="sxs-lookup"><span data-stu-id="84002-513">Data Loss Prevention policy tips are not supported on 3rd party cloud apps</span></span>|
|<span data-ttu-id="84002-514">**On-prem**</span><span class="sxs-lookup"><span data-stu-id="84002-514">**On-prem**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="84002-515">なし</span><span class="sxs-lookup"><span data-stu-id="84002-515">None</span></span>|<span data-ttu-id="84002-516">なし</span><span class="sxs-lookup"><span data-stu-id="84002-516">None</span></span>||
|<span data-ttu-id="84002-517">**Word、Excel、Win32 PowerPointクライアント**</span><span class="sxs-lookup"><span data-stu-id="84002-517">**Word, Excel, PowerPoint Win32 Client**</span></span>|:::image type="icon" source="../media/crsmrk.png" border="false":::|<span data-ttu-id="84002-518">Subset</span><span class="sxs-lookup"><span data-stu-id="84002-518">Subset</span></span>|<span data-ttu-id="84002-519">Subset</span><span class="sxs-lookup"><span data-stu-id="84002-519">Subset</span></span>|<span data-ttu-id="84002-520">サポートされる[機密情報Outlook一](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types)覧については、一部の機密情報の種類に関するポリシー ヒントのみを示すデスクトップ 上の Office アプリとデスクトップ 上の Office アプリのサポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84002-520">Please see [Outlook 2013 and later and Office apps on Desktop support showing policy tips for only some sensitive information types](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) for the list of sensitive information types supported</span></span></br></br><span data-ttu-id="84002-521">WXP クライアント アプリのポリシー ヒントは、以下または DLP ポリシー内の条件またはアクションのサブセットを正確に持つすべての DLP ポリシーについて、Sharepoint Online または One Drive for Business Sites に保存されているドキュメントで機能します。</span><span class="sxs-lookup"><span data-stu-id="84002-521">Policy tips for WXP client apps will work for documents stored on Sharepoint Online or One Drive for Business Sites for all DLP policies which have exactly the below or a subset of conditions or actions in the DLP policy:</span></span></br> <ul><li><span data-ttu-id="84002-522">コンテンツには機密情報の種類が含まれる</span><span class="sxs-lookup"><span data-stu-id="84002-522">Content contains sensitive information types</span></span></li><li><span data-ttu-id="84002-523">Access Scope (コンテンツは内部/外部で共有されます)</span><span class="sxs-lookup"><span data-stu-id="84002-523">Access Scope (Content is shared internally/externally)</span></span></li><li><span data-ttu-id="84002-524">ユーザーに通知する (ポリシー ヒント/ユーザー通知)</span><span class="sxs-lookup"><span data-stu-id="84002-524">Notify User (policy tips/user notifications)</span></span></li><li><span data-ttu-id="84002-525">すべてのユーザーをブロックする</span><span class="sxs-lookup"><span data-stu-id="84002-525">Block everyone</span></span></li><li><span data-ttu-id="84002-526">インシデント レポート</span><span class="sxs-lookup"><span data-stu-id="84002-526">Incident reports</span></span></li></ul></br> <span data-ttu-id="84002-527">その他の条件やアクションが存在する場合、そのポリシーの DLP ポリシー ヒントは Word、Excel、または PowerPoint のデスクトップ アプリには表示されません。</span><span class="sxs-lookup"><span data-stu-id="84002-527">If any other condition or action is present, the DLP policy tip for that policy will not appear in the desktop apps of Word, Excel or PowerPoint.</span></span></br><span data-ttu-id="84002-528">詳細[については、「Excel、PowerPoint、Word のポリシー ヒント」](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84002-528">See [Policy tips in Excel, PowerPoint, and Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) for more details</span></span>|
||||||
