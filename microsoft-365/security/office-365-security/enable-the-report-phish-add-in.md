---
title: レポートフィッシング アドインを有効にする
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 個々のユーザーまたは組織全体に対して、Outlookおよび web Outlookレポート フィッシング アドインを有効にする方法について説明します。
ms.openlocfilehash: 44fa55a82462de336982d3af2e3996c14699fd7c
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625391"
---
# <a name="enable-the-report-phishing-add-in"></a>レポート フィッシング アドインを有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Exchange Online メールボックスを持つ Microsoft 365 組織の管理者である場合は、セキュリティ & コンプライアンス センターで申請ポータルを使用することをお勧めします。 詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。

web 上の Outlook および Outlook 用のレポート メッセージおよびレポートフィッシング アドイン (以前は Outlook Web App) を使用すると、ユーザーは誤検知 (悪いマークが付いた良いメール) または誤検知 (悪いメールが許可されている) を Microsoft とその関連会社に簡単に報告して分析できます。

Microsoft では、これらの申請を使用して、電子メール保護テクノロジの有効性を向上します。 たとえば、ユーザーがレポート フィッシング アドインを使用して多くのメッセージを報告するとします。 この情報は、セキュリティ ダッシュボード [や他のレポート](security-dashboard.md) に表示されます。 組織のセキュリティ チームは、この情報をフィッシング対策ポリシーを更新する必要がある可能性を示す指標として使用できます。

[レポート メッセージ] アドインまたは [レポート フィッシング] アドインをインストールできます。 ユーザーがスパム メッセージとフィッシング メッセージの両方を報告する場合は、組織にレポート メッセージ アドインを展開します。 詳細については、「レポート メッセージ [アドインを有効にする」を参照してください](enable-the-report-message-add-in.md)。

[フィッシングの報告] アドインには、フィッシング メッセージのみを報告するオプションがあります。 管理者は組織のレポート フィッシング アドインを有効にし、個々のユーザーが自分でインストールできます。

個々のユーザーである場合は、自分でレポート フィッシング [アドインを有効にできます](#get-the-report-phishing-add-in-for-yourself)。

グローバル管理者または Exchange Online 管理者で、Exchange が OAuth 認証を使用するように構成されている場合は、組織のレポート フィッシング アドインを[有効にできます](#get-and-enable-the-report-phishing-add-in-for-your-organization)。 [レポートフィッシング] Add-Inは、集中展開 [を通じて利用できます](../../admin/manage/centralized-deployment-of-add-ins.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- レポート フィッシング アドインは、ほとんどのサブスクリプションとMicrosoft 365製品で動作します。

  - Outlook on the web
  - Outlook 2013 SP1 以降
  - Outlook 2016 for Mac以降
  - OutlookアプリにMicrosoft 365含まれているEnterprise
  - Outlook iOS と Android 用のアプリ

- レポート フィッシング アドインは、オンプレミスの組織の共有メールボックスまたはメールボックスExchangeできません。

- 指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。 詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。

- 既存の Web ブラウザーは、レポート フィッシング アドインで動作する必要があります。 ただし、アドインが使用できないか、期待通り動作していない場合は、別のブラウザーを試してください。

- 組織のインストールでは、OAuth 認証を使用するように組織を構成する必要があります。 詳細については、「アドインの集中展開が組織で機能するかどうかを判断する」 [を参照してください](../../admin/manage/centralized-deployment-of-add-ins.md)。

- 管理者は、グローバル管理者役割グループのメンバーである必要があります。 詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

## <a name="get-the-report-phishing-add-in-for-yourself"></a>自分でレポートフィッシング アドインを取得する

1. [Microsoft AppSource] に移動し、レポートフィッシング <https://appsource.microsoft.com/marketplace/apps> アドインを検索します。

2. [今 **すぐ取得] をクリックします**。

3. 表示されるダイアログで、使用条件とプライバシー ポリシーを確認し、[続行] を **クリックします**。

4. 仕事用または学校用のアカウント (ビジネス用) または Microsoft アカウント (個人用) を使用してサインインします。

アドインをインストールして有効にすると、次のアイコンが表示されます。

- このOutlookアイコンは次のように表示されます。

  ![アプリの [フィッシング アドインのレポート] Outlook](../../media/Outlook-ReportPhishing.png)

- Web Outlookすると、アイコンは次のように表示されます。

  ![Outlookの [フィッシング レポート] アドイン アイコンをクリックします。](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a>組織のレポート フィッシング アドインを取得して有効にする

> [!NOTE]
> アドインが組織に表示するには、最大で 12 時間かかる場合があります。

1. Microsoft 365 管理センターで **、[設定** アドイン] ページの [アドイン] ページに移動します。アドイン ページが表示されない場合は、[統合アプリ] ページの上部にある \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **[設定** \>  \> 統合アプリ アドイン] リンクに移動します。

2. ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を **選択します**。

   ![管理センターの [サービスとアドイン] ページMicrosoft 365ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. 表示される **[新しいアドインの展開]** フライアウトで、情報を確認し、[次へ] を **クリックします**。

4. 次のページで、[ストアから **選択] をクリックします**。

   ![新しいアドイン ページの展開](../../media/NewAddInScreen2.png)

5. 表示される **[アドインの選択**] ページで、[検索]ボックスをクリックし、[レポートフィッシング] と入力し、[検索検索] アイコン **を** ![ クリックします ](../../media/search-icon.png) 。 結果の一覧で[レポートフィッシング] **を探し、[** 追加] を **クリックします**。

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

   完了したら、[展開] を **クリックします**。

8. 表示される **[レポートフィッシングの** 展開] ページに、進行状況レポートが表示され、その後にアドインが展開されたという確認が表示されます。 情報を読んだら、[次へ] を **クリックします**。

9. 表示される **[アドインのアナウンス] ページ** で、情報を確認し、[閉じる] を **クリックします**。

## <a name="learn-how-to-use-the-report-phishing-add-in"></a>レポート フィッシング アドインの使い方について

アドインが割り当てられているユーザーには、次のアイコンが表示されます。

- このOutlookアイコンは次のように表示されます。

  ![アプリの [フィッシング アドインのレポート] Outlook](../../media/Outlook-ReportPhishing.png)

- Web Outlookすると、アイコンは次のように表示されます。

  ![Outlook Web レポートフィッシング アドイン アイコンで確認する](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>レポートフィッシング アドインの設定を確認または編集する

1. Microsoft 365 管理センターで **、[設定** アドイン] ページの [アドイン] ページに移動します。アドイン ページが表示されない場合は、[統合アプリ] ページの上部にある \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **[設定** \>  \> 統合アプリ アドイン] リンクに移動します。

2. [フィッシング のレポート] **アドインを検索して** 選択します。

3. 組織に **合った設定を** 表示、確認、および編集する [レポートのフィッシングの編集] フライアウトで行います。 完了したら、**[保存]** をクリックします。

## <a name="view-and-review-reported-messages"></a>報告されたメッセージの表示と確認

ユーザーが Microsoft に報告するメッセージを確認するには、次のオプションがあります。

- 管理者申請ポータルを使用します。 詳細については [、「Microsoft へのユーザー申請の表示」を参照してください](admin-submission.md#view-user-submissions-to-microsoft)。

- 報告されたメッセージのコピーを送信するメール フロー ルール (トランスポート ルールとも呼ばれる) を作成します。 手順については、「メール フロー ルールを使用して、ユーザーが Microsoft に報告している [情報を確認する」を参照してください](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)。
