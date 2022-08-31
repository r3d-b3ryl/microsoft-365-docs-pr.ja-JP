---
title: 報告されたメッセージの管理者によるレビュー
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 報告されたメッセージを確認し、ユーザーにフィードバックを送信する方法について説明します。
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: aad0bf6d34b8a23a0461e3fb55987450f178da40
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483500"
---
# <a name="admin-review-for-reported-messages"></a>報告されたメッセージの管理者によるレビュー

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange OnlineメールボックスとMicrosoft Defender for Office 365を持つ Microsoft 365 組織では、管理者は報告されたメッセージを確認した後、テンプレート化されたメッセージをエンド ユーザーに返送できるようになりました。 テンプレートは、組織に合わせてカスタマイズでき、管理者の評決にも基づいてカスタマイズできます。

この機能は、ユーザーにフィードバックを提供するように設計されていますが、システム内のメッセージの判定は変更されません。 Microsoft がフィルターを更新して改善できるようにするには、管理送信を使用して分析用にメッセージ[を送信](admin-submission.md)する必要があります。

メッセージが [偽陽性または偽陰性](report-false-positives-and-false-negatives.md)として報告された場合にのみ、ユーザーにレビュー結果をマークして通知できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

- ユーザー申請の構成を変更するには、次のいずれかの役割グループのメンバーである必要があります。
  - [Microsoft 365 Defender ポータル](permissions-microsoft-365-security-center.md)の組織の管理またはセキュリティ管理者。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)の組織管理。

- また、Exchange Online PowerShell にアクセスする必要もあります。 使用しようとしているアカウントに PowerShell Exchange Onlineアクセスできない場合は、*ドメイン内の電子メール アドレスを指定* するというエラーが表示されます。 Exchange Online PowerShell へのアクセスを有効または無効にする方法の詳細については、次のトピックを参照してください。
  - [Exchange Online PowerShell へのアクセスを有効または無効にする](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Exchange Onlineのクライアント アクセス規則](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="notify-users-from-within-the-portal"></a>ポータル内からユーザーに通知する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**Email & コラボレーション** \> **申請]** の [**申請]** ページに移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **ユーザーから報告されたメッセージ**] をクリックし、マークして通知するメッセージを選択します。

3. [ **マークと通知** ] ドロップダウンを選択し、[ **脅威が見つかりません**]、[ **フィッシング]**、または **[迷惑メール]** の順に選択します。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/admin-review-send-message-from-portal.png" alt-text="ユーザーから報告されたメッセージを表示するページ" lightbox="../../media/admin-review-send-message-from-portal.png":::

報告されたメッセージは、偽陽性または偽陰性としてマークされ、メッセージを報告したユーザーに通知する電子メールがポータル内から自動的に送信されます。

## <a name="customize-the-messages-used-to-notify-users"></a>ユーザーに通知するために使用するメッセージをカスタマイズする

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ユーザー申請**] ページの **[Email & コラボレーション** \> ポリシー] & **[ルール** \> **脅威ポリシー** \> **] [ユーザーが報告したメッセージの設定****] セクション** に移動します。 **[ユーザー申請]** ページに直接移動するには、 <https://security.microsoft.com/userSubmissionsReportMessage>.

2. [**ユーザー申請**] ページで、送信者の表示名を指定する場合は、[**管理者レビュー結果** のEmail通知] セクション **の [送信者として使用する電子メール アドレスOffice 365指定** する] チェック ボックスをオンにし、使用する名前を入力します。 Outlook に表示される電子メール アドレスとすべての返信がそこに移動します。

3. いずれかのテンプレートをカスタマイズする場合は、ページの下部にある [ **電子メール通知のカスタマイズ** ] をクリックします。 開いたポップアップでは、次の内容のみをカスタマイズできます。

    - フィッシング詐欺
    - 迷惑メール
    - 脅威は検出されませんでした
    - フッター

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/admin-review-customize-message.png" alt-text="[確認メッセージのカスタマイズ] ページ" lightbox="../../media/admin-review-customize-message.png":::

4. 完了したら、**[保存]** をクリックします。 これらの値をクリアするには、[**ユーザー申請**] ページで **[破棄**] をクリックします。
