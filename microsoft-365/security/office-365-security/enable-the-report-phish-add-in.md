---
title: フィッシング報告アドインを有効にする
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
description: 個々のユーザーまたは組織全体に対して、Outlook および Outlook on the web の Report Phishing アドインを有効にする方法について説明します。
ms.openlocfilehash: 6d86fdc710539bc3c74eb94f8931ca48a0c992c1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029140"
---
# <a name="enable-the-report-phishing-add-in"></a>レポート フィッシング アドインを有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Exchange Online メールボックスを使用している Microsoft 365 組織の管理者である場合は、セキュリティ/コンプライアンス センターの提出ポータルを&勧めします。 詳細については、「管理者送信を使用して、疑わしいスパム、 [フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。

Outlook および Outlook on the web (旧称 Outlook Web App) 用の Report Message and Report Phishing アドインを使用すると、分析のために誤検知 (良いメールが悪いとマークされている) や検出検出 (不正な電子メールを許可) を Microsoft とその関連会社に簡単に報告できます。

Microsoft は、これらの申請を使用して、電子メール保護テクノロジの有効性を向上します。 たとえば、ユーザーが Report Phishing アドインを使用して多数のメッセージを報告するとします。 この情報は、セキュリティ ダッシュボード [および他のレポート](security-dashboard.md) に表示されます。 組織のセキュリティ チームは、この情報を、フィッシング対策ポリシーの更新が必要になる可能性があるという指標として使用できます。

レポート メッセージ アドインまたは Report Phishing アドインをインストールできます。 ユーザーがスパム メッセージとフィッシング メッセージの両方を報告する場合は、組織にレポート メッセージ アドインを展開します。 詳細については、「メッセージ報告 [アドインを有効にする」を参照してください](enable-the-report-message-add-in.md)。

Report Phishing アドインは、フィッシング メッセージのみを報告するオプションを提供します。 管理者は組織の Report Phishing アドインを有効にし、個々のユーザーが自分でインストールできます。

個人ユーザーの場合は、自分で [Report Phishing アドインを有効にできます](#get-the-report-phishing-add-in-for-yourself)。

グローバル管理者または Exchange Online 管理者で、Exchange が OAuth 認証を使用するように構成されている場合は、組織の Report [Phishing アドインを有効にできます](#get-and-enable-the-report-phishing-add-in-for-your-organization)。 Report Phishing Add-Inは、一元展開 [で利用できます](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- レポート フィッシング アドインは、ほとんどの Microsoft 365 サブスクリプションと次の製品で動作します。

  - Outlook on the web
  - Outlook 2013 SP1 以降
  - Outlook 2016 for Mac
  - エンタープライズ向け Microsoft 365 アプリに含まれる Outlook

- レポート フィッシング アドインは、オンプレミスの Exchange 組織のメールボックスでは使用できません。

- 指定したメールボックスにコピーまたはリダイレクトされる報告されたメッセージを構成できます。 詳細については、「ユーザー提出 [ポリシー」を参照してください](user-submission.md)。

- 既存の Web ブラウザーは、Report Phishing アドインで動作する必要があります。 ただし、アドインが使用できないか、期待通り動作しない場合は、別のブラウザーを試してください。

- 組織のインストールでは、OAuth 認証を使用するように組織を構成する必要があります。 詳細については、「アドインの一元展開が組織で機能するかどうかを判断する」 [を参照してください](../../admin/manage/centralized-deployment-of-add-ins.md)。

- 管理者は、グローバル管理者役割グループのメンバーである必要があります。 詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

## <a name="get-the-report-phishing-add-in-for-yourself"></a>自分用の Report Phishing アドインを取得する

1. Microsoft AppSource に移動し <https://appsource.microsoft.com/marketplace/apps> 、フィッシング報告アドインを検索します。

2. [今 **すぐ取得] をクリックします**。

3. 表示されるダイアログで、使用条件とプライバシー ポリシーを確認し、[続行] をクリック **します**。

4. (業務用) または Microsoft アカウント (個人使用の場合) を使用してサインインします。

アドインをインストールして有効にすると、次のアイコンが表示されます。

- Outlook では、アイコンは次のように表示されます。

  ![Outlook のフィッシング報告アドイン アイコン](../../media/Outlook-ReportPhishing.png)

- Outlook on the web では、アイコンは次のように表示されます。

  ![Outlook on the web Report Phishing アドイン アイコン](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a>組織の Report Phishing アドインを取得して有効にする

> [!NOTE]
> アドインが組織に表示されるには、最大で 12 時間かかる場合があります。

1. Microsoft 365 管理センターで、[設定アドイン] ページに移動します。[アドイン] ページが表示されな場合は、[統合アプリ] ページの上部にある [統合アプリアドインの設定] リンクに移動します。 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  

2. ページ **の上部にある [アドインの** 展開] を選択し、[次へ] を選択 **します**。

   ![Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. 表示される **新しいアドイン の展開** のフライアウトで、情報を確認し、[次へ] をクリック **します**。

4. 次のページで、[ストアから **選択] をクリックします**。

   ![新しいアドイン ページを展開する](../../media/NewAddInScreen2.png)

5. 表示される **[アドインの選択**] ページで、[検索]ボックスをクリックし、「Report **Phishing」** と入力して、[検索検索] アイコン **を** ![ クリックします ](../../media/search-icon.png) 。 結果の一覧で[レポートフィッシング] **を** 見つけ、[追加] をクリック **します**。

6. 表示されるダイアログで、ライセンスとプライバシー情報を確認し、[続行] をクリック **します**。

7. 表示される **[アドインの構成]** ページで、次の設定を構成します。

   - **割り当てられたユーザー**: 次のいずれかの値を選択します。

     - **すべてのユーザー** (既定)
     - **特定のユーザー/グループ**
     - **私だけです**

   - **展開方法**: 次のいずれかの値を選択します。

     - **固定 (既定値)**: アドインは指定されたユーザーに自動的に展開され、削除できない。
     - **Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.
     - **オプション**: アドインは指定されたユーザーに自動的に展開されますが、削除することもできます。

   完了したら、[展開] をクリック **します**。

8. 表示 **される [レポートフィッシング** の展開] ページに、進行状況レポートの後に、アドインが展開されたという確認が表示されます。 情報を読んだら、[次へ] を **クリックします**。

9. 表示された **[アドインのアナウンス** ] ページで情報を確認し、[閉じる] をクリック **します**。

## <a name="learn-how-to-use-the-report-phishing-add-in"></a>レポート フィッシング アドインの使い方について

アドインが割り当てられているユーザーには、次のアイコンが表示されます。

- Outlook では、アイコンは次のように表示されます。

  ![Outlook のフィッシング報告アドイン アイコン](../../media/Outlook-ReportPhishing.png)

- Outlook on the web では、アイコンは次のように表示されます。

  ![Outlook on the Web Report Phishing Add-in アイコン](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>レポート フィッシング アドインの設定を確認または編集する

1. Microsoft 365 管理センターで、[設定アドイン] ページに移動します。[アドイン] ページが表示されな場合は、[統合アプリ] ページの上部にある [統合アプリの設定] リンクに移動します。 \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \>  

2. フィッシング報告アドイン **を見つけて** 選択します。

3. 組織に **応じて表示** 、確認、および編集の設定を行う [レポートフィッシングの編集] フライアウトで。 完了したら、**[保存]** をクリックします。

## <a name="view-and-review-reported-messages"></a>報告されたメッセージの表示と確認

ユーザーが Microsoft に報告するメッセージを確認するには、次のオプションがあります。

- 管理者提出ポータルを使用します。 詳細については、「Microsoft へのユーザー [申請の表示」を参照してください](admin-submission.md#view-user-submissions-to-microsoft)。

- メール フロー ルール (トランスポート ルールとも呼ばれる) を作成して、報告されたメッセージのコピーを送信します。 手順については、「メール フロー ルール [を使用して、ユーザーが Microsoft に報告している情報を確認する」を参照してください](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)。