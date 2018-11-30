---
title: '手順 9: パスワードの更新を簡素化する'
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
description: ハイブリッド環境でのパスワードの書き戻しについて理解し、構成します。
ms.openlocfilehash: 55da101ca729de804ae76dafbe35a46969af9d8d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869181"
---
# <a name="step-9-simplify-password-updates"></a><span data-ttu-id="952a5-103">手順 9: パスワードの更新を簡素化する</span><span class="sxs-lookup"><span data-stu-id="952a5-103">Step 9: Simplify password updates</span></span>

<span data-ttu-id="952a5-104">*この手順はハイブリッド環境でオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="952a5-104">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="952a5-p101">この手順では、ユーザーが Azure Active Directory (AD) からパスワードをリセットできるようにします。リセットされたパスワードはローカル Windows Server Active Directory (AD) にレプリケートされます。これは、パスワードの書き戻しと呼ばれます。パスワードの書き戻しにより、ユーザーはユーザー アカウントとその属性が保存されているオンプレミス Windows Server AD でパスワードを更新する必要がなくなります。これは、オンプレミス ネットワークにリモート アクセス接続できないローミング ユーザーやリモート ユーザーにとって役立ちます。</span><span class="sxs-lookup"><span data-stu-id="952a5-p101">In Step 9, you'll allow users to reset their passwords through Azure Active Directory (AD), which is then replicated to your local Windows Server Active Directory (AD). This process is known as password writeback. With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where user accounts and their attributes are stored. This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="952a5-109">パスワードの書き戻しは、Identity Protection 機能 (アカウント侵害が発生する可能性が高い危険が検出された場合にオンプレミス パスワードの変更をユーザーに義務付けるなど) を最大限に活用するために必要です。</span><span class="sxs-lookup"><span data-stu-id="952a5-109">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="952a5-110">その他の情報と構成手順については、「[Azure AD SSPR とパスワード書き戻し](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="952a5-110">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="952a5-p102">最適なエクスペリエンスとリリースされた新機能を利用できるようにするため、Azure AD Connect の最新バージョンにアップグレードします。詳細については、「[Azure AD Connect のカスタム インストール](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="952a5-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

<span data-ttu-id="952a5-113">中間チェックポイントとして、この手順の[終了条件](identity-exit-criteria.md#crit-identity-pw-writeback)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="952a5-113">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="952a5-114">次の手順</span><span class="sxs-lookup"><span data-stu-id="952a5-114">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [<span data-ttu-id="952a5-115">ユーザー サインインを簡素化する</span><span class="sxs-lookup"><span data-stu-id="952a5-115">Simplify user sign-in</span></span>](identity-single-sign-on.md) |

