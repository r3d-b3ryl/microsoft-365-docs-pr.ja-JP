---
title: レポート メッセージ アドインを有効にする
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: 個々のユーザーまたは組織全体で、Outlook および outlook on the web 用のレポートメッセージアドインを有効にする方法について説明します。
ms.openlocfilehash: 0024e8c87ef6326c1df4547349631c4f1fd4cab8
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921578"
---
# <a name="enable-the-report-message-add-in"></a>レポート メッセージ アドインを有効にする

> [!NOTE]
> Exchange Online メールボックスを使用している組織内の管理者である場合は、セキュリティ & コンプライアンスセンターで送信ポータルを使用することをお勧めします。 詳細については、「[管理者による送信を使用して疑わしいスパム、フィッシング、url、およびファイルを Microsoft に送信する](admin-submission.md)」を参照してください。

Outlook 用のレポートメッセージアドインと web 上の Outlook (旧称 Outlook Web App) を使用すると、ユーザーは、誤検知 (不良としてマークされた良好な電子メール) や誤検知 (無効な電子メールが許可されている) を Microsoft および分析のための関連会社に簡単に報告できます。 Microsoft では、これらの送信を使用して、電子メール保護テクノロジの有効性を向上させています。

たとえば、ユーザーが大量のメッセージをフィッシングとして報告しているとします。 この情報は、[セキュリティダッシュボード](security-dashboard.md)やその他のレポートに表示されます。 組織のセキュリティチームは、この情報を、フィッシング対策ポリシーの更新が必要になる可能性があることを示すものとして使用できます。 または、レポートメッセージアドインを使用して迷惑メールではないというフラグが付いたメッセージを多数報告している場合は、組織のセキュリティチームが[スパム対策ポリシー](configure-your-spam-filter-policies.md)を調整する必要があります。

さらに、組織で[Office 365 Advanced Threat Protection プラン 1](office-365-atp.md)または[Plan 2](office-365-ti.md)を使用している場合は、レポートメッセージアドインにより、組織のセキュリティチームに対して、セキュリティポリシーの確認と更新に使用できる有用な情報が提供されます。

管理者は、組織に対してレポートメッセージアドインを有効にすることができます。また、個々のユーザーが自分でこのアドインをインストールすることもできます。

個人ユーザーの場合は、[レポートメッセージアドインを自分自身に対して有効に](#get-the-report-message-add-in-for-yourself)することができます。

グローバル管理者または Exchange Online 管理者であり、Exchange が OAuth 認証を使用するように構成されている場合は、[組織に対してレポートメッセージアドインを有効](#get-and-enable-the-report-message-add-in-for-your-organization)にすることができます。 これで、レポートメッセージアドインが[一元展開](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)によって利用可能になりました。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- レポートメッセージアドインは、ほとんどの Microsoft 365 サブスクリプションと、次の製品で機能します。

  - Outlook on the web
  - Outlook 2013 SP1 以降
  - Outlook 2016 for Mac
  - Outlook は、Microsoft 365 apps for Enterprise に含まれています。

- レポートメッセージアドインは現在、次の場合には使用できません。

  - オンプレミスの Exchange 組織内のメールボックス
  - GCC、GCC HIGH、または DoD サブスクリプション

- 指定したメールボックスに、レポートされたメッセージをコピーまたはリダイレクトするように構成できます。 詳細については、「 [Office 365 でスパムおよびフィッシングのメッセージをユーザーが送信するためのメールボックスを指定](user-submission.md)する」を参照してください。

- 既存の web ブラウザーは、レポートメッセージアドインと共に動作する必要があります。 しかし、アドインが使用できない、または正常に動作しないことが判明した場合は、別のブラウザーを試してみてください。

- 組織をインストールするには、OAuth 認証を使用するように組織を構成する必要があります。 詳細については、「[組織でアドインの一元展開が機能するかどうかを判断](../../admin/manage/centralized-deployment-of-add-ins.md)する」を参照してください。

- 管理者は、グローバル管理者役割グループのメンバーである必要があります。 詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

## <a name="get-the-report-message-add-in-for-yourself"></a>自分用のレポートメッセージアドインを取得する

1. Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps>に移動し、レポートメッセージアドインを検索します。 レポートメッセージアドインに直接移動するには、に<https://appsource.microsoft.com/product/office/wa104381180>移動します。

2. [**今すぐダウンロード**] をクリックします。

   ![レポートメッセージ-今すぐ取得](../../media/ReportMessageGETITNOW.png)

3. 表示されるダイアログで、使用条件とプライバシーポリシーを確認し、[**続行**] をクリックします。

4. 職場または学校アカウントを使用してサインインします (一般法人向け)。または Microsoft アカウント (個人使用)。

アドインがインストールされて有効になると、次のアイコンが表示されます。

- Outlook のアイコンは、次のように表示されます。

  ![Outlook のレポートメッセージアドインアイコン](../../media/OutlookReportMessageIcon.png)

- Web 上の Outlook では、アイコンは次のようになります。

  ![Outlook on the web レポートメッセージアドインアイコン](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

アドインの使用方法については、「[レポートメッセージアドインを使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)する」を参照してください。

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>組織のレポートメッセージアドインを取得して有効にする

> [!NOTE]
> 組織にアドインが表示されるまで、最大で12時間かかる場合があります。

1. Microsoft 365 管理センターで、[ **Services & アドイン**] ページ<https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>に移動し、[**アドインの展開**] をクリックします。

   ![Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. [**新しいアドインの展開**] ポップアップが表示されたら、情報を確認して、[**次へ**] をクリックします。

3. 次のページで、[**ストアから選択**] をクリックします。

   ![新しいアドインページを展開する](../../media/NewAddInScreen2.png)

4. [**アドインの選択**] ページが表示されたら、**検索**ボックスをクリックして、[**レポートメッセージ**] と入力し](../../media/search-icon.png)、[**検索** ![検索] アイコンをクリックします。 結果の一覧で、[**レポート] メッセージ**を見つけ、[**追加**] をクリックします。

   ![アドインの検索結果を選択する](../../media/NewAddInScreen3.png)

5. 表示されるダイアログで、ライセンスとプライバシーの情報を確認し、[**続行**] をクリックします。

6. [**アドインの構成**] ページが表示されたら、次の設定を構成します。

   - [**割り当て済みのユーザー**]: 次のいずれかの値を選択します。

     - **Everyone** (既定)
     - **特定のユーザー/グループ**
     - **私だけです**

   - **展開方法**: 次のいずれかの値を選択します。

     - **Fixed (既定)**: アドインは、指定されたユーザーに自動的に展開され、削除することはできません。
     - **利用可能**: ユーザーは、**自宅** \> **Get add-ins** \>でアドインをインストールできます。**管理者が管理**するアドイン
     - **省略可能**: アドインは指定されたユーザーに自動的に展開されますが、削除することもできます。

   ![アドインページを構成する](../../media/configure-add-in.png)

   完了したら、[**配置**] をクリックします。

7. [**レポートメッセージの展開**] ページに、進行状況レポートの後に、アドインが展開されたことを示す確認が表示されます。 情報を読み終えたら、[**次へ**] をクリックします。

   ![レポートのメッセージを展開するページ](../../media/deploy-report-message-page.png)

8. 表示される [**アドインのアナウンス**] ページで情報を確認し、[**閉じる**] をクリックします。

   ![アドインページをアナウンスする](../../media/announce-add-in-page.png)

### <a name="learn-how-to-use-the-report-message-add-in"></a>レポートメッセージアドインの使用方法について説明します。

アドインに割り当てられているユーザーには、次のアイコンが表示されます。

- Outlook のアイコンは、次のように表示されます。

  ![Outlook のレポートメッセージアドインアイコン](../../media/OutlookReportMessageIcon.png)

- Web 上の Outlook では、アイコンは次のようになります。

  ![Outlook on the Web レポートメッセージアドインアイコン](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

レポートメッセージアドインについてユーザーに通知する場合は、[レポートメッセージアドインを使用](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)するためのリンクを含めます。

### <a name="review-or-edit-settings-for-the-report-message-add-in"></a>レポートメッセージアドインの設定を確認または編集する

1. Microsoft 365 管理センターで、[ **Services & アドイン**] ページに移動<https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>します。

   ![新しい Microsoft 365 管理センターの [サービスとアドイン] ページ](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. **レポートメッセージ**アドインを検索して選択します。

3. 表示される [**レポートメッセージの編集**] ポップアップで、組織に合わせて設定を確認して編集します。 完了したら、**[保存]** をクリックします。

   ![レポートメッセージアドインの設定](../../media/EditReportMessageAddIn.png)
