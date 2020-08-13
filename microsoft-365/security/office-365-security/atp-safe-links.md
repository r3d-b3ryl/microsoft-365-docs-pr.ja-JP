---
title: ATP の安全なリンク機能
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: この記事では、安全なリンクを使用して組織をフィッシングやその他の攻撃から保護する方法について説明します。
ms.openlocfilehash: 5baf18c249d67551c7ae1eeb643a401ea16d2b6c
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656983"
---
# <a name="atp-safe-links"></a>ATP の安全なリンク機能

## <a name="overview-of-office-365-atp-safe-links"></a>Office 365 の ATP の安全なリンクの概要

> [!IMPORTANT]
> この記事は、[Office 365 Advanced Threat Protection](office-365-atp.md) をご利用の法人のお客様を対象としています。 Outlook.com、Microsoft 365 ファミリ、または Microsoft 365 Personal を使用していて、Outlook での安全なリンクに関する情報をお探しの場合は、「 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。

Office 365 の ATP の安全なリンク ( [office 365 Advanced Threat Protection](office-365-atp.md)の一部) は、[電子メールメッセージ](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-email)や[Office ドキュメント](how-atp-safe-links-works.md#how-atp-safe-links-works-with-urls-in-office-documents)内の web アドレス (url) の確認時間を提供することにより、組織を保護するのに役立ちます。 保護は、Microsoft 365 セキュリティチームによって設定された[ATP Safe Links ポリシー](set-up-atp-safe-links-policies.md)によって定義されます。

ATP の安全なリンクポリシーが確立されると、全体管理者、セキュリティ管理者、およびセキュリティ閲覧者は、 [Advanced Threat Protection のレポートを表示](view-reports-for-atp.md)できるようになります。 これらのレポートの情報は、セキュリティチームが組織を保護したり、セキュリティインシデントを研究したりするために、さらに手順を実行するのに役立ちます。

[新機能が atp に追加される](office-365-atp.md#new-features-in-office-365-atp)と、Microsoft 365 セキュリティチームが組織の[atp の安全なリンクポリシー](set-up-atp-safe-links-policies.md)を追加または編集できるようになります。 また、新しく改訂された[警告ページ](atp-safe-links-warning-pages.md)や Outlook でのネイティブリンクのレンダリングなどの変更点や改善点に注目することがあります (Microsoft 365 Apps for enterprise version 1809 で導入されました)。

## <a name="how-to-get-atp-safe-links-protection"></a>ATP の安全なリンク保護を取得する方法

**最初に、サブスクリプションに[Office 365 Advanced Threat Protection](office-365-atp.md)が含まれていることを確認し**てください。プラン1またはプラン2。 Office 365 ATP は、サブスクリプションに含まれています ( [microsoft 365 Enterprise e5](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 Business Premium](https://www.microsoft.com/microsoft-365/business)、office 365 Enterprise E5、office 365 教育 A5 など)。Office 365 ATP を含まない Microsoft 365 サブスクリプションが組織にある場合は、ATP をアドオンとして購入する可能性があります。 詳細については、以下を参照してください。 

- [Office 365 Advanced Threat Protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)

- [Office 365 Advanced Threat Protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

**次に、ATP の安全なリンクポリシーが定義**されていることを確認します。 (「 [Office 365 ATP 安全リンクポリシーを](set-up-atp-safe-links-policies.md)セットアップする」を参照してください)。ATP の安全なリンク機能は、次の場合にアクティブになります。

- ATP の安全なリンクポリシーは、電子メールと Office ドキュメント用に設定されています。 (「 [ATP の安全なリンクポリシーを設定](set-up-atp-safe-links-policies.md)する」を参照してください)。

- Microsoft 365 クライアントアプリは先進認証を使用するように構成されています (これは、Office ドキュメントでの ATP の安全なリンク保護のためです)。 (「 [Office 2016 のモダン認証」を](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)参照してください)。

- ユーザーが職場または学校のアカウントを使用してサインインしている。 (「 [Office へのサインイン」を](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426)参照してください)。

- 組織の電子メールは、Exchange Online Protection を通過します。

**また、必要なアクセス許可があることを確認して**ください。 ATP ポリシーを定義 (または編集) するには、適切な役割が割り当てられている必要があります。 次の表では、いくつかの例について説明します。

****

|役割|参照先/割り当て方法|
|---|---|
|グローバル管理者|Microsoft 365 の購入にサインアップするユーザーは、既定ではグローバル管理者になります。 (詳細については、 [Microsoft 365 管理者の役割につい](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)てを参照してください)。|
|セキュリティ管理者|Azure Active Directory 管理センター (<https://aad.portal.azure.com>)|
|Exchange Online 組織の管理|Exchange 管理センター (<https://outlook.office365.com/ecp>) <br>または <br>  PowerShell コマンドレット (「[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)」を参照してください)|
|

## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a>ATP の安全なリンク保護が適切であることを確認する方法

全体管理者またはセキュリティ管理者として、 [ATP の安全なリンクポリシー](set-up-atp-safe-links-policies.md)を定期的に確認してください。 ATP の安全なリンクポリシーは、保護を電子メールメッセージのみのハイパーリンクに適用するか、Office ドキュメント内の Url にも適用するかを決定します。

ATP 安全なリンクポリシーが確立されると、組織のセキュリティチームは、 [Advanced Threat protection のレポートを表示](view-reports-for-atp.md)することによって、組織のために Atp の安全なリンク保護がどのように機能しているかを確認できます。

## <a name="example-scenarios"></a>シナリオ例

次の表では、ATP の安全なリンク保護が適用される可能性がある、または導入されていない可能性があるシナリオの例を示します。 (これらすべての場合において、組織に Office 365 Enterprise E5 があると想定しています)。

****

|シナリオ例|この場合、ATP の安全なリンク保護が適用されますか。|
|---|---|
|田中は、電子メールおよび Office ドキュメント内の Url を対象とする、ATP の安全なリンクポリシーを持つグループのメンバーです。 田中は、他のユーザーが送信した PowerPoint プレゼンテーションを開き、プレゼンテーション内の URL をクリックします。|はい。 定義されている ATP の安全なリンクポリシーは、田中のグループ、田中の電子メール、および Word、Excel、PowerPoint、または Visio ドキュメントに適用されるため、田中がサインインしており、Microsoft 365 Apps for enterprise for Windows、iOS、Android デバイスで使用している場合に限ります。|
|Chris の組織では、グローバルまたはセキュリティ管理者がまだ ATP の安全なリンクポリシーを定義していません。 Chris は、悪意のある web サイトへの URL を含む電子メールを受信します。 Chris は、URL が悪意があることを認識しないので、リンクをクリックします。|いいえ。 組織内のすべてのユーザーの Url を対象とする既定のポリシーは、保護を確立するために定義する必要があります。|
|Pat の組織では、グローバルまたはセキュリティ管理者は、まだ ATP の安全なリンクポリシーを定義または編集していません。 [Pat] Word 文書を開き、ファイル内の URL をクリックします。|いいえ。 Office ドキュメントを含むポリシーは、保護を確立するために定義する必要があります。 「 [Set UP ATP Safe Links policies In Office 365」を](set-up-atp-safe-links-policies.md)参照してください。|
|Lee の組織には、 `https://tailspintoys.com` ブロックされた web サイトとしてリストされている、ATP の安全なリンクポリシーがあります。 Lee は、の URL が含まれる電子メールメッセージを受信 `https://tailspintoys.com/aboutus/trythispage` します。 Lee が URL をクリックします。|これは、サイト全体とそのすべてのサブページがブロックする Url の一覧に含まれているかどうかによって決まります。 「 [ATP Safe Links を使用してカスタムのブロックされた url リストをセットアップする](set-up-a-custom-blocked-urls-list-atp.md)」を参照してください。|
|田中の仕事仲間は、電子メールが悪意のある URL を含んでいることを知らずに、田中に電子メールを送信します。|これは、組織内で送信される電子メールに ATP の安全なリンクポリシーが定義されているかどうかによって決まります。 「 [Set UP ATP Safe Links policies In Office 365」を](set-up-atp-safe-links-policies.md)参照してください。|
|
