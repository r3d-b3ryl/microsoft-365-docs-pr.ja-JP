---
title: 試用版ラボまたはMicrosoft 365 Defender環境をセットアップする
description: ポータルMicrosoft 365 Defenderアクセスし、試用版ラボ環境Microsoft 365 Defenderセットアップする
keywords: Microsoft 365 Defenderセットアップ、パイロットMicrosoft 365 Defender、評価ラボのMicrosoft 365 Defender、Microsoft 365 Defender試す
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 681d9798c6f16f5829bdb4e5272abc3eac719a59
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2022
ms.locfileid: "64500983"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a>ラボ環境でMicrosoft 365 Defender試用版をセットアップする 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender 

このトピックでは、専用のラボ環境をセットアップする方法について説明します。 実稼働環境での試用版のセットアップの詳細については、新しい評価とパイロット ガイド[をMicrosoft 365 Defender](eval-overview.md)してください。 

## <a name="create-an-office-365-e5-trial-tenant"></a>試用版テナントOffice 365 E5作成する
>[!NOTE]
>既存のサブスクリプションまたはサブスクリプションが既にOffice 365場合Azure Active Directory試用版テナントの作成手順Office 365 E5スキップできます。

1. [製品ポータル] Office 365 E5 [に移動し、[](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)無料試用版] **を選択します**。

   :::image type="content" source="../../media/mtp-eval-9.png" alt-text="[無料Office 365 E5] ページ" lightbox="../../media/mtp-eval-9.png":::
  
2. 電子メール アドレス (個人または企業) を入力して、試用版の登録を完了します。 [アカウント **の設定] をクリックします**。

   :::image type="content" source="../../media/mtp-eval-10.png" alt-text="[Office 365 E5登録のセットアップ] ページ" lightbox="../../media/mtp-eval-10.png":::

3. 名、名、会社の電話番号、会社名、会社の規模、国または地域を入力します。  

   :::image type="content" source="../../media/mtp-eval-11.png" alt-text="名前Office 365 E5電話、会社の詳細を求める [試用版の登録設定] ページ" lightbox="../../media/mtp-eval-11.png":::
   
   > [!NOTE]
   > ここで設定した国または地域によって、ホストされるデータ センター Office 365決定されます。
  
4. 確認の基本設定を選択します。テキスト メッセージまたは通話を使用します。 [検証 **コードの送信] をクリックします**。 

   :::image type="content" source="../../media/mtp-eval-12.png" alt-text="検証Office 365 E5確認を求める[試用版の登録のセットアップ] ページ" lightbox="../../media/mtp-eval-12.png":::

5. テナントのカスタム ドメイン名を設定し、[次へ] を **クリックします**。

   :::image type="content" source="../../media/mtp-eval-13.png" alt-text="カスタム Office 365 E5を設定できる [試用版の登録セットアップ] ページ" lightbox="../../media/mtp-eval-13.png":::
 
6. テナントのグローバル管理者になる最初の ID を設定します。 [名前] **と [パスワード]** を **入力します**。 [**サインアップ**] をクリックします。

   :::image type="content" source="../../media/mtp-eval-14.png" alt-text="ビジネスOffice 365 E5を設定できる試用版登録のセットアップ ページ" lightbox="../../media/mtp-eval-14.png":::

7. [**セットアップに移動] を** クリックして、Office 365 E5のプロビジョニングを完了します。

   :::image type="content" source="../../media/mtp-eval-15.png" alt-text="[Office 365 E5に移動する] をクリックするように求める [試用版の登録のセットアップ] ページ" lightbox="../../media/mtp-eval-15.png":::

8. ConnectドメインをテナントにOffice 365します。 [省略可能][**Connect所有しているドメインを選択し、** ドメイン名を入力します。 **[次へ]** をクリックします。

   :::image type="content" source="../../media/mtp-eval-16.png" alt-text="サインインOffice 365 E5メールをカスタマイズする必要がある [ユーザー設定] ページ" lightbox="../../media/mtp-eval-16.png":::
 
9. TXT レコードまたは MX レコードを追加して、ドメインの所有権を検証します。 ドメインに TXT レコードまたは MX レコードを追加したら、[確認] を選択 **します**。

   :::image type="content" source="../../media/mtp-eval-17.png" alt-text="ドメインOffice 365 E5する MX レコードの TXT を追加する必要がある[設定] ページ" lightbox="../../media/mtp-eval-17.png":::
 
10. [省略可能]テナントのユーザー アカウントを作成します。 [次へ] をクリックすると、この手順を **スキップできます**。

    :::image type="content" source="../../media/mtp-eval-18.png" alt-text="ユーザー Office 365 E5追加できる [ユーザー設定] ページ" lightbox="../../media/mtp-eval-18.png":::
 
11. [省略可能]アプリOfficeダウンロードします。 [次 **へ] を** クリックして、この手順をスキップします。 

    :::image type="content" source="../../media/mtp-eval-19.png" alt-text="アプリOffice 365 E5インストールできる [Office] ページ" lightbox="../../media/mtp-eval-19.png":::

12. [省略可能]電子メール メッセージを移行します。 繰り返しますが、この手順は省略できます。

    :::image type="content" source="../../media/mtp-eval-20.png" alt-text="電子Office 365 E5メッセージを移行するかどうかを設定できる場所を示します。" lightbox="../../media/mtp-eval-20.png":::
 
13. [オンライン サービス] を選択します。 [次 **Exchange] を** 選択し、[次へ] **をクリックします**。 

    :::image type="content" source="../../media/mtp-eval-21.png" alt-text="オンライン Office 365 E5を選択できる場所" lightbox="../../media/mtp-eval-21.png":::

14. ドメインに MX、CNAME、TXT レコードを追加します。 完了したら、[確認] を **選択します**。

    :::image type="content" source="../../media/mtp-eval-22.png" alt-text="ここでOffice 365 E5 DNS レコードを追加できます" lightbox="../../media/mtp-eval-22.png":::
 
15. おめでとうございます、テナントのプロビジョニングOffice 365完了です。

    :::image type="content" source="../../media/mtp-eval-23.png" alt-text="[Office 365 E5完了確認] ページ" lightbox="../../media/mtp-eval-23.png":::
    

## <a name="enable-microsoft-365-trial-subscription"></a>試用版サブスクリプションMicrosoft 365有効にする

>[!NOTE]
>試用版にサインアップすると、1 か月間 25 のユーザー ライセンスを使用できます。 詳細[については、「Try or buy a Microsoft 365サブスクリプション」](../../commerce/try-or-buy-microsoft-365.md)を参照してください。

1. [[Microsoft 365 管理] で、[](https://admin.microsoft.com/)課金] **をクリック** し、[サービスの購入] **に移動します**。

2. [無料 **Microsoft 365 E5] を** 選択し、[無料試用版の **開始] をクリックします**。 

   :::image type="content" source="../../media/mtp-eval-24.png" alt-text="[無料Microsoft 365 E5開始] ページ" lightbox="../../media/mtp-eval-24.png":::

3. 確認の基本設定を選択します。テキスト メッセージまたは通話を使用します。 決定したら、電話番号を入力し、選択内容に応じて [テキスト] または [電話] を選択します。

   :::image type="content" source="../../media/mtp-eval-25.png" alt-text="[Microsoft 365 E5無料試用版の開始] ページで、ロボットではないことを証明するコードを送信する連絡先の詳細を求める" lightbox="../../media/mtp-eval-25.png":::
 
4. 確認コードを入力し、[無料試用版 **の開始] をクリックします**。

   :::image type="content" source="../../media/mtp-eval-26.png" alt-text="[Microsoft 365 E5無料試用版の開始] ページで、システムが送信した検証コードを入力して、ロボットではないことを証明できます。" lightbox="../../media/mtp-eval-26.png":::

5. [**今すぐ試す**] をクリックして、Microsoft 365 E5確認します。

   :::image type="content" source="../../media/mtp-eval-27.png" alt-text="[Microsoft 365 E5無料試用版を開始する] ページで、[今すぐ試す] ボタンを起動する必要があります。" lightbox="../../media/mtp-eval-27.png":::
 
6. **CenterUsersActive** >  **ユーザー Microsoft 365 管理に** > **移動します**。 ユーザー アカウントを選択し、[製品ライセンスの **管理**] を選択し、ライセンスを [ライセンス] から [**Office 365 E5 Microsoft 365 E5。** **[保存]** をクリックします。

   :::image type="content" source="../../media/mtp-eval-28.png" alt-text="[Microsoft 365 管理センター] ページで、ライセンスをMicrosoft 365 E5できます。" lightbox="../../media/mtp-eval-28.png":::
 
7. グローバル管理者アカウントを再度選択し、[ユーザー名の管理] **をクリックします**。

   :::image type="content" source="../../media/mtp-eval-29.png" alt-text="[アカウントMicrosoft 365 管理ユーザー名の管理] を選択できる [アカウント センター] ページ" lightbox="../../media/mtp-eval-29.png":::

8. [省略可能]前の手順で *onmicrosoft.com* に応じて、ドメインをドメインから独自のドメインに変更します。 **[変更の保存]** をクリックします。

   :::image type="content" source="../../media/mtp-eval-30.png" alt-text="ドメインMicrosoft 365 管理変更できる [センター] ページ" lightbox="../../media/mtp-eval-30.png":::

## <a name="next-step"></a>次のステップ
|[フェーズ 3: オンボードで&する](config-m365d-eval.md) | お客様のMicrosoft 365 Defenderラボまたはパイロット環境Microsoft 365 Defender、エンドポイントのオンボードに関する各柱を構成します。
|:-------|:-----|
