---
title: '手順 6: 資格情報が侵害されないように保護する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD Identity Protection について理解し、構成します。
ms.openlocfilehash: b1dea9d2917c45bf87bd972f56c9eac2b074c252
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869643"
---
# <a name="step-6-protect-against-credential-compromise"></a><span data-ttu-id="56677-103">手順 6: 資格情報が侵害されないように保護する</span><span class="sxs-lookup"><span data-stu-id="56677-103">Step 6: Protect against credential compromise</span></span>

<span data-ttu-id="56677-104">*この手順はオプションであり、Microsoft 365 Enterprise の E5 バージョンにのみ適用されます。*</span><span class="sxs-lookup"><span data-stu-id="56677-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="56677-p101">この手順では、資格情報を侵害から保護するポリシーを構成する方法を説明します。資格情報の侵害では、攻撃者がユーザーのアカウント名とパスワードを把握し、組織のクラウド サービスとデータへのアクセスを獲得します。Azure AD Identity Protection には、攻撃者によるアカウントやグループ間の水平移動と、その後の最も価値の高いデータへの移動を防止するための手段が多数あります。</span><span class="sxs-lookup"><span data-stu-id="56677-p101">In Step 15, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data. Azure AD Identity Protection provides a number of ways to help prevent an attacker from moving laterally through your accounts and groups, and subsequently, to your most valuable data.</span></span>

<span data-ttu-id="56677-107">Azure AD Identity Protection では次の作業を実行できます。</span><span class="sxs-lookup"><span data-stu-id="56677-107">With Azure AD Identity Protection, you can:</span></span>

|||
|:---------|:---------|
|<span data-ttu-id="56677-108">組織の ID における潜在的な脆弱性の洗い出しと対処</span><span class="sxs-lookup"><span data-stu-id="56677-108">Determine and address potential vulnerabilities in your organization’s identities</span></span>|<span data-ttu-id="56677-p102">Azure AD では、機械学習を使用して異常や不審なアクティビティ (サインインとサインイン後の活動など) を検出します。Identity Protection はこのデータを使用して、問題の評価と対処の実施に役立つレポートとアラートを生成します。</span><span class="sxs-lookup"><span data-stu-id="56677-p102">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities. Using this data, Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="56677-111">組織の ID に関連する不審なアクションの検出と自動対応</span><span class="sxs-lookup"><span data-stu-id="56677-111">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="56677-p103">指定されているリスク レベルに達した時点で、検出された問題に対し自動的に対応するリスクベースのポリシーを構成できます。このリスクベースのポリシーと、Azure Active Directory および Enterprise Mobility + Security (EMS) の他の条件付きアクセス制御との組み合わせにより、自動的にアクセスをブロックするか、または修正処置 (パスワード リセットと後続のサインインでの多要素認証の義務付けなど) を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="56677-p103">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached. These policies, in addition to other conditional access controls provided by Azure Active Directory and Enterprise Mobility + Security (EMS), can either automatically block access or take corrective actions, including password resets and requiring multi-factor authentication for subsequent sign-ins.</span></span>|
|<span data-ttu-id="56677-114">不審なインシデントを調査し、管理操作によって解決する</span><span class="sxs-lookup"><span data-stu-id="56677-114">Investigate suspicious incidents and resolve them with administrative actions</span></span>|<span data-ttu-id="56677-p104">セキュリティ インシデントに関する情報を使用して、リスク イベントを調査できます。調査の追跡と修復処理 (パスワードのリセットなど) の開始のための基本的なワークフローを利用できます。</span><span class="sxs-lookup"><span data-stu-id="56677-p104">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span>|

<span data-ttu-id="56677-117">[Azure AD Identity Protection の詳細情報](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56677-117">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="56677-118">[Azure AD Identity Protection を有効にする手順](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56677-118">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

<span data-ttu-id="56677-119">この手順の結果として、Azure AD Identity Protection が有効になり、次の目的で Azure AD Identity Protection を使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="56677-119">The results of this step are that you've enabled Azure AD Identity protection and you are using it to:</span></span>

- <span data-ttu-id="56677-120">潜在的な ID の脆弱性に対処する。</span><span class="sxs-lookup"><span data-stu-id="56677-120">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="56677-121">資格情報の侵害の疑いがあるものを検出する。</span><span class="sxs-lookup"><span data-stu-id="56677-121">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="56677-122">発生している不審な ID インシデントを調査して対処する。</span><span class="sxs-lookup"><span data-stu-id="56677-122">Investigate and address ongoing suspicious identity incidents.</span></span>

|||
|:-------|:-----|
|![Microsoft クラウド のテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="56677-124">テスト ラボ ガイド: Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="56677-124">Test Lab Guide: Azure AD Identity Protection</span></span>](azure-ad-identity-protection-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="56677-125">中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-ident-prot)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="56677-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-ident-prot) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="56677-126">次の手順</span><span class="sxs-lookup"><span data-stu-id="56677-126">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)| [<span data-ttu-id="56677-127">ディレクトリを同期する</span><span class="sxs-lookup"><span data-stu-id="56677-127">Synchronize directories</span></span>](identity-azure-ad-connect.md) |


