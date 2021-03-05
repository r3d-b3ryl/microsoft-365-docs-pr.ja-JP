---
title: レポート メッセージ アドインを有効にする
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Outlook および Outlook on the web 用のレポート メッセージ アドインを、個々のユーザーまたは組織全体で有効にする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5eed0fc8905020ea12d3fa6a51c5c8051205b0da
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453755"
---
# <a name="enable-the-report-message-add-in"></a>レポート メッセージ アドインを有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> Exchange Online メールボックスを使用する Microsoft 365 組織の管理者である場合は、セキュリティ & コンプライアンス センターで申請ポータルを使用することをお勧めします。 詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。

Outlook および Outlook on the web (以前は Outlook Web App と呼ばれる) のレポート メッセージとレポートフィッシング アドインを使用すると、ユーザーは誤検知 (悪いとマークされた良いメール) または誤検知 (悪いメールが許可されている) を Microsoft とその関連会社に簡単に報告して分析できます。

Microsoft では、これらの申請を使用して、電子メール保護テクノロジの有効性を向上します。 たとえば、レポート メッセージ アドインを使用して迷惑メールとしてフラグが設定されたメッセージが多く報告されている場合、組織のセキュリティ チームはスパム対策ポリシーを調整する必要があります。 [](configure-your-spam-filter-policies.md)

[レポート メッセージ] アドインまたは [レポート フィッシング] アドインをインストールできます。 ユーザーにフィッシング メッセージのみを報告する場合は、組織にレポートフィッシング アドインを展開します。 詳細については、「レポートフィッシング [アドインを有効にする」を参照してください](enable-the-report-phish-add-in.md)。

レポート メッセージ アドインには、スパム メッセージとフィッシング メッセージの両方を報告するオプションがあります。 管理者は、組織のレポート メッセージ アドインを有効にし、個々のユーザーが自分でインストールできます。

個々のユーザーの場合は、自分でレポート メッセージ [アドインを有効にできます](#get-the-report-message-add-in-for-yourself)。

グローバル管理者または Exchange Online 管理者で、Exchange が OAuth 認証を使用するように構成されている場合は、組織でレポート メッセージ アドイン [を有効にできます](#get-and-enable-the-report-message-add-in-for-your-organization)。 [レポート メッセージ] Add-Inは、集中展開 [を通じて利用できます](../../admin/manage/centralized-deployment-of-add-ins.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- レポート メッセージ アドインは、ほとんどの Microsoft 365 サブスクリプションと次の製品で動作します。

  - Outlook on the web
  - Outlook 2013 SP1 以降
  - Outlook 2016 for Mac
  - エンタープライズ向け Microsoft 365 アプリに含まれる Outlook
  - iOS と Android 用 Outlook アプリ

- レポート メッセージ アドインは、オンプレミスの Exchange 組織の共有メールボックスまたはメールボックスでは使用できません。

- 指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。 詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。

- 既存の Web ブラウザーは、レポート メッセージ アドインで動作する必要があります。 ただし、アドインが使用できないか、期待通り動作していない場合は、別のブラウザーを試してください。

- 組織のインストールでは、OAuth 認証を使用するように組織を構成する必要があります。 詳細については、「アドインの集中展開が組織で機能するかどうかを判断する」 [を参照してください](../../admin/manage/centralized-deployment-of-add-ins.md)。

- 管理者は、グローバル管理者役割グループのメンバーである必要があります。 詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

## <a name="get-the-report-message-add-in-for-yourself"></a>自分でレポート メッセージ アドインを取得する

1. [Microsoft AppSource] に移動し <https://appsource.microsoft.com/marketplace/apps> 、レポート メッセージ アドインを検索します。 レポート メッセージ アドインに直接移動するには、に移動します <https://appsource.microsoft.com/product/office/wa104381180> 。

2. [今 **すぐ取得] をクリックします**。

   ![レポート メッセージ - 今すぐ取得する](../../media/ReportMessageGETITNOW.png)

3. 表示されるダイアログで、使用条件とプライバシー ポリシーを確認し、[続行] を **クリックします**。

4. 仕事用または学校用のアカウント (ビジネス用) または Microsoft アカウント (個人用) を使用してサインインします。

アドインをインストールして有効にすると、次のアイコンが表示されます。

- Outlook では、アイコンは次のように表示されます。

  ![Outlook のレポート メッセージ アドイン アイコン](../../media/OutlookReportMessageIcon.png)

- Outlook on the web では、アイコンは次のように表示されます。

  ![Outlook on the web Report Message add-in icon](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

アドインの使い方については、「レポート メッセージ アドインを使用 [する」を参照してください](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>組織のレポート メッセージ アドインを取得して有効にする

> [!NOTE]
> アドインが組織に表示するには、最大で 12 時間かかる場合があります。

1. Microsoft 365 管理センターで、[設定アドイン] ページの [アドイン] ページに移動し、[アドイン] ページが表示しない場合は、[統合アプリ] ページの上部にある [設定統合アプリ アドイン] リンクに移動します。 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  

2. ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を **選択します**。

   ![Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. 表示される **[新しいアドインの展開]** フライアウトで、情報を確認し、[次へ] を **クリックします**。

4. 次のページで、[ストアから **選択] をクリックします**。

   ![新しいアドイン ページの展開](../../media/NewAddInScreen2.png)

5. 表示される **[アドインの選択] ページ** で、[検索]ボックスをクリックし、[レポート メッセージ] と入力し、[検索検索] アイコン **を** ![ クリックします ](../../media/search-icon.png) 。 結果の一覧で、[レポート メッセージ] **を探し、[** 追加] を **クリックします**。

   ![アドインの検索結果を選択する](../../media/NewAddInScreen3.png)

6. 表示されるダイアログで、ライセンスとプライバシー情報を確認し、[続行] を **クリックします**。

7. 表示される **[アドインの構成]** ページで、次の設定を構成します。

   - **割り当てられたユーザー**: 次のいずれかの値を選択します。

     - **すべてのユーザー** (既定)
     - **特定のユーザー/グループ**
     - **私だけです**

   - **展開方法**: 次のいずれかの値を選択します。

     - **固定 (既定)**: 指定したユーザーにアドインが自動的に展開され、削除できない。
     - **利用可能**: ユーザーは、ホーム アドイン \> **の取得** 管理でアドイン \> **をインストールできます**。
     - **オプション**: アドインは指定したユーザーに自動的に展開されますが、削除を選択できます。

   ![[アドインの構成] ページ](../../media/configure-add-in.png)

   完了したら、[展開] を **クリックします**。

8. 表示される **[レポート メッセージの展開** ] ページに、進行状況レポートが表示され、その後にアドインが展開されたという確認が表示されます。 情報を読んだら、[次へ] を **クリックします**。

   ![[レポート メッセージの展開] ページ](../../media/deploy-report-message-page.png)

9. 表示される **[アドインのアナウンス] ページ** で、情報を確認し、[閉じる] を **クリックします**。

   ![[アドインのアナウンス] ページ](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>レポート メッセージ アドインの使い方について

アドインが割り当てられているユーザーには、次のアイコンが表示されます。

- Outlook では、アイコンは次のように表示されます。

  ![Outlook の [レポート メッセージ アドイン] アイコン](../../media/OutlookReportMessageIcon.png)

- Outlook on the web では、アイコンは次のように表示されます。

  ![Outlook on the Web Report Message Add-in icon](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

レポート メッセージ アドインについてユーザーに通知する場合は、[レポート メッセージ アドインを使用する] へのリンク [を含める必要があります](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)。

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>レポート メッセージ アドインの設定を確認または編集する

1. Microsoft 365 管理センターで、[設定アドイン] ページの [アドイン] ページに移動し、[アドイン] ページが表示しない場合は、[統合アプリ] ページの上部にある [設定統合アプリ アドイン] リンクに移動します。 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  

   ![新しい Microsoft 365 管理センターAdd-Insの [サービスとサービス] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. レポート メッセージ アドインを **検索して** 選択します。

3. 表示される **[レポート メッセージの編集** ] フライアウトで、組織に合った設定を確認および編集します。 完了したら、**[保存]** をクリックします。

   ![レポート メッセージ アドインの設定](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>報告されたメッセージの表示と確認

ユーザーが Microsoft に報告するメッセージを確認するには、次のオプションがあります。

- 管理者申請ポータルを使用します。 詳細については [、「Microsoft へのユーザー申請の表示」を参照してください](admin-submission.md#view-user-submissions-to-microsoft)。

- 報告されたメッセージのコピーを送信するメール フロー ルール (トランスポート ルールとも呼ばれる) を作成します。 手順については、「メール フロー ルールを使用して、ユーザーが Microsoft に報告している [情報を確認する」を参照してください](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。
