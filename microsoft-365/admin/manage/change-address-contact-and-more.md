---
title: 組織の住所およびその他のプロファイル情報を変更する
f1.keywords:
- CSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: tugu, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- commerce_billing
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid: MET150
description: 組織名、住所、電話、技術連絡先、電子メールなど、組織プロファイルを変更します。
ms.date: 02/11/2022
ms.openlocfilehash: 4c5fdda4a2f089afc7e63a570290fdc08dc46440
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63316647"
---
# <a name="change-your-organizations-address-technical-contact-and-more"></a>組織の住所およびその他のプロファイル情報を変更する
  
組織名、住所、電話番号、技術担当者の連絡先など、組織のプロファイルの変更を行うことができます。 **この情報を更新するには、全体管理者でなければなりません。**
  
請求書またはサブスクリプションに関連付けられているアドレスを変更するには、「[ビジネス向けのMicrosoft 365の請求先住所を変更する」を参照してください](../../commerce/billing-and-payments/change-your-billing-addresses.md)。

## <a name="change-organization-settings-for-cloud-pcs"></a>クラウド PC の組織設定を変更する

既定では、新しいクラウド PC は Windows 11 オペレーティング システムと標準ユーザー アカウントの種類で作成されます。 これらの既定の設定を変更するには、次の手順に従います。

1. グローバル管理者アカウントを使用してMicrosoft 365 管理センターにサインインします。
2. **[設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**組織の設定]**</a> ページに移動します。
3. [**サービス**] タブで、**Windows 365** を選択します。
4. 優先するオペレーティング システムとアカウントの種類を選択し、[ **保存**] を選択します。

組織の設定は、新しく作成されたクラウド PC にのみ適用されます。 これらの設定を変更しても、既存のクラウド PC の OS やアカウントの種類は変更されません。

## <a name="edit-organization-information"></a>会社情報の編集

> [!IMPORTANT]
> サブスクリプションの国または地域は、変更できません。 これは、組織の本社所在地の国または地域によって、利用可能なサービス、税金、請求通貨、およびデータセンターの場所が決まるためです。 組織の国または地域を変更する場合は、新しいアカウントのサインアップを実行して、希望する国または地域を選択し、新しいサブスクリプションを購入してください。

会社のプロファイル ページで他の情報を変更するには:
  
1. 管理センターで、[**設定** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**組織の設定]**</a> ページに移動します。
2. **[組織プロファイル]** タブで **[組織情報]** を選択します。
3. 組織の情報を更新し、**[変更を保存]** を選択します。 変更を保存できるようにするには、* のマークが付いたすべての必須フィールドに必ず入力してください。

以下に、各フィールドの説明を示します。

## <a name="what-do-these-fields-mean"></a>各フィールドの意味

|**Field**  |**説明**  |
|---------|---------|
|名前  <br/>   | ここで入力する名前は、次に示すページでユーザーに表示されます。  <br/>  サインイン ページ: ユーザーが勤務先または学校のメール アドレスでその他の Microsoft アカウントを設定した場合、サインイン ページに組織名が表示される可能性があります。これによって、ユーザーは 職場や学校のアカウント とその他のアカウントを区別できるようになるため、サインインするときにどちらのアカウントを使用するか識別できます。  <br/>  組織プロファイルのリンクとページ: 組織のプロファイルへのリンクには組織名が表示されます。  <br/>  Yammerナビゲーション: Yammerでは、左側のナビゲーションでは、ホーム Yammer ネットワークの名前として組織名が使用されます。  <br/> OneDrive 同期 クライアント: 組織名は、mac の Windows と Finder のエクスプローラー、ファイル パス、OneDrive アクティビティ センター、OneDriveクラウド アイコンのツールヒント、OneDrive設定ウィンドウに表示されます。 現時点では、組織名を更新しても、構成されたクライアントの組織名は更新されません。 <br/> MS Teams: Teamsの組織スイッチャーに組織名が表示される <br/>  |
|住所、市区町村、都道府県、郵便番号  <br/>     | ここに入力した住所は、請求書に表示されます。[販売先]: 請求書の販売先住所は、プロファイル ページの組織の住所と同じです ([ビジネス向けの請求書または請求書のMicrosoft 365を理解するを](../../commerce/billing-and-payments/understand-your-invoice2.md)参照してください。  <br/>        |
|国または地域  <br/>    | これは、会社の本社が置かれている国または地域です。国または地域を選択すると、利用できるサービス、国または地域での税と請求通貨、および最寄りのデータ センターの場所が特定されます (「[ライセンスによる使用制限について](https://office.microsoft.com/redir/FX103037529)」を参照してください)。  <br/>注: 選択した後、国または地域を変更することはできません。 選択を変更する場合は、サブスクリプションをキャンセルして、もう一度サインアップする必要があります。 このプロセスのヘルプについては、 [サポートにお問い合わせください](../../business-video/get-help-support.md)。        |
|電話  <br/>     | 会社の代表番号です。通常は、会社の本社の番号です。  <br/>        |
|技術担当者の連絡先  <br/> |これは、Microsoft 365 サブスクリプションを管理する主要な技術担当者の電子メール アドレスです。 これは、Microsoft 365サービスの状態に関する通信を受け取るユーザーです。  <br/> |
|優先する言語  <br/> |優先する言語によって、Microsoft からユーザー組織に送信されるすべての通信の言語が決まります。サインアップすると、この設定によって、SharePoint Online で使用される言語 (チーム サイトでユーザーに表示される) が決まります。サインアップ後に言語の優先順位設定を変更した場合、その後の通信はすべて、最後に選択した言語によって送信されます。    <br/> 注: SharePoint Online で使用される言語は変更できません。           |

## <a name="change-your-alternate-email-address"></a>代替メール アドレスを変更する

管理者は、パスワードをリセットするための代替メール アドレスを変更できます。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a>に戻ります。

2. ヘッダーでプロファイル アイコンを選択し、[ **アカウントの表示**] を選択します。

3. 左側の [ **セキュリティ情報**] を選択します。

4. [電子メール] セクションで、[**変更**] を選択します。

5. **[代替メール**] ボックスでアドレスを編集し、[**次へ**] を選択します。

6. 代替メール アドレスに送信されたコードを入力し、[ **OK] を** 選択して変更を確認します。
その他のプロファイル情報の変更については、「 [連絡先の設定を変更する](change-contact-preferences.md) 」または「 [表示言語を変更](https://support.microsoft.com/office/6f238bff-5252-441e-b32b-655d5d85d15b)する」を参照してください。
  
### <a name="email-signatures"></a>メールの署名
  
メールの署名は、Outlook Web App で変更できます。詳細については、「[メールの設定](https://support.microsoft.com/office/30c69a79-efc6-42d2-b740-4bf1c1f8a01c)」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[別のアドレスからメールを送信する](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (記事)\
[ユーザー名とメール アドレスを変更する](../add-users/change-a-user-name-and-email-address.md) (記事)\
[Microsoft 365 でメールの転送を構成する](../email/configure-email-forwarding.md) (記事)
