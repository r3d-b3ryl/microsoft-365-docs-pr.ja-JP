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
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 44476e7a8ad3bad9b21e82a9528593ceb350257d
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470903"
---
# <a name="admin-review-for-reported-messages"></a>報告されたメッセージの管理者によるレビュー

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange OnlineメールボックスとMicrosoft Defender for Office 365を持つMicrosoft 365組織では、管理者は報告されたメッセージを確認した後、テンプレート化されたメッセージをエンド ユーザーに返送できるようになりました。 テンプレートは、組織に合わせてカスタマイズでき、管理者の評決にも基づいてカスタマイズできます。

この機能は、ユーザーにフィードバックを提供するように設計されていますが、システム内のメッセージの判定は変更されません。 Microsoft がフィルターを更新して改善できるようにするには、管理者の申請を使用して分析用にメッセージを送信する必要 [があります](admin-submission.md)。

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

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**Email & collaboration** \> **Submissions]** の [**申請]** ページに移動します。 **[申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **ユーザーから報告されたメッセージ**] をクリックし、マークして通知するメッセージを選択します。

3. [ **マークと通知** ] ドロップダウンを選択し、[ **脅威が見つかりません**]、[ **フィッシング]**、または **[迷惑メール]** の順に選択します。

   > [!div class="mx-imgBorder"]
   > :::image type="content" source="../../media/admin-review-send-message-from-portal.png" alt-text="ユーザーから報告されたメッセージを表示するページ" lightbox="../../media/admin-review-send-message-from-portal.png":::

報告されたメッセージは、偽陽性または偽陰性としてマークされ、メッセージを報告したユーザーに通知する電子メールがポータル内から自動的に送信されます。

## <a name="customize-the-messages-used-to-notify-users"></a>ユーザーに通知するために使用するメッセージをカスタマイズする

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**電子メール & コラボレーション** \> ポリシー] & [**ルール** \> **の脅威ポリシー** \> **] [ユーザーが報告したメッセージの設定****] セクションの** [**ユーザー申請**] ページに移動します。 **[ユーザー申請]** ページに直接移動するには、 <https://security.microsoft.com/userSubmissionsReportMessage>.

2. [**ユーザー申請**] ページで、送信者の表示名を指定する場合は、[**管理者レビューの結果の電子メール通知**] セクション **の [送信者として使用Office 365電子メール アドレスを指定** する] チェック ボックスをオンにし、使用する名前を入力します。 Outlookに表示される電子メール アドレスとすべての返信がそこに移動します。

3. いずれかのテンプレートをカスタマイズする場合は、ページの下部にある [ **電子メール通知のカスタマイズ** ] をクリックします。 開いたポップアップでは、次の内容のみをカスタマイズできます。

    - フィッシング詐欺
    - 迷惑メール
    - 脅威は検出されませんでした
    - フッター

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="../../media/admin-review-customize-message.png" alt-text="[確認メッセージのカスタマイズ] ページ" lightbox="../../media/admin-review-customize-message.png":::

4. 完了したら、**[保存]** をクリックします。 これらの値をクリアするには、[**ユーザー申請**] ページで **[破棄**] をクリックします。
