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
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 23a1c49ac7b0e8a12fa8d473f880981a1daa7955
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58568566"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a>ラボ環境でMicrosoft 365 Defender試用版をセットアップする 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender 

このトピックでは、専用のラボ環境をセットアップする方法について説明します。 実稼働環境での試用版のセットアップの詳細については、新しい評価とパイロット ガイド[をMicrosoft 365 Defender](eval-overview.md)してください。 

## <a name="create-an-office-365-e5-trial-tenant"></a>試用版テナントOffice 365 E5作成する
>[!NOTE]
>既存のサブスクリプションまたはサブスクリプションが既Office 365場合Azure Active Directory試用版テナントの作成手順Office 365 E5スキップできます。

1. [製品ポータル] に [Office 365 E5し、[](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)無料試用版]**を選択します**。

   ![Image of_Office 365 E5 無料試用版ページ。](../../media/mtp-eval-9.png)
  
2. 電子メール アドレス (個人または企業) を入力して、試用版の登録を完了します。 [アカウント **の設定] をクリックします**。

   ![Image of_Office 365 E5 試用版登録のセットアップ ページ。](../../media/mtp-eval-10.png)

3. 名、名、会社の電話番号、会社名、会社の規模、国または地域を入力します。  

   ![名前、電話Office会社の詳細を求める画像 of_Office 365 E5 試用版登録セットアップ ページ。](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > ここで設定した国または地域によって、ホストされるデータ センター Office 365決定されます。
  
4. 確認の基本設定を選択します。テキスト メッセージまたは通話を使用します。 [検証 **コードの送信] をクリックします**。 

   ![検証の設定をOfficeする 365 E5 試用版登録セットアップ ページの画像。](../../media/mtp-eval-12.png)

5. テナントのカスタム ドメイン名を設定し、[次へ] を **クリックします**。

   ![Image of_Officeカスタム ドメイン名を設定できる 365 E5 試用版登録セットアップ ページです。](../../media/mtp-eval-13.png)
 
6. テナントのグローバル管理者になる最初の ID を設定します。 [名前] **と [パスワード]** を **入力します**。 [**サインアップ**] をクリックします。

   ![ビジネス ID をOfficeできる Image of_Office 365 E5 試用版登録セットアップ ページ。](../../media/mtp-eval-14.png)

7. [**セットアップに移動] を** クリックして、Office 365 E5プロビジョニングを完了します。

   ![[Go setup] Office 365 E5をクリックするように求める[試用版登録のセットアップ] ページのイメージ。](../../media/mtp-eval-15.png)

8. ConnectドメインをテナントにOffice 365します。 [省略可能]**[Connect所有しているドメインを選択し、** ドメイン名を入力します。 [**次へ**] をクリックします。

   ![Image of_Office 365 E5 セットアップ ページで、サインインとメールをカスタマイズする必要があります。](../../media/mtp-eval-16.png)
 
9. TXT レコードまたは MX レコードを追加して、ドメインの所有権を検証します。 ドメインに TXT レコードまたは MX レコードを追加したら、[確認] を **選択します**。

   ![Image of_Office 365 E5 セットアップ ページで、ドメインを確認するために MX レコードの TXT を追加する必要があります。](../../media/mtp-eval-17.png)
 
10. [省略可能]テナントのユーザー アカウントを作成します。 [次へ] をクリックすると、この手順を **スキップできます**。

    ![Image of_Office 365 E5 セットアップ ページで、ユーザーを追加できます。](../../media/mtp-eval-18.png)
 
11. [省略可能]アプリOfficeダウンロードします。 [次 **へ] を** クリックして、この手順をスキップします。 

    ![Image of_Office 365 E5 ページで、アプリをインストールOfficeできます。](../../media/mtp-eval-19.png)

12. [省略可能]電子メール メッセージを移行します。 繰り返しますが、この手順は省略できます。

    ![Image of_Office 365 E5 電子メール メッセージを移行するかどうかを設定できます。](../../media/mtp-eval-20.png)
 
13. [オンライン サービス] を選択します。 [次 **Exchange] を** 選択し、[次へ]**をクリックします**。 

    ![Image of_Office 365 E5 オンライン サービスを選択できます。](../../media/mtp-eval-21.png)

14. ドメインに MX、CNAME、TXT レコードを追加します。 完了したら、[確認] を **選択します**。

    ![Image of_Office 365 E5 ここでは、DNS レコードを追加できます。](../../media/mtp-eval-22.png)
 
15. おめでとうございます、テナントのプロビジョニングOffice 365完了です。

    ![Image of_Office 365 E5 セットアップ完了確認ページ。](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>試用版サブスクリプションMicrosoft 365有効にする

>[!NOTE]
>試用版にサインアップすると、1 か月間 25 のユーザー ライセンスを使用できます。 詳細 [については、「Try or Buy a M365 サブスクリプション」](../../commerce/try-or-buy-microsoft-365.md) を参照してください。

1. [[Microsoft 365 管理センター] で、[](https://admin.microsoft.com/)課金]**をクリック** し、[サービスの購入]**に移動します**。

2. [無料 **Microsoft 365 E5] を** 選択し、[無料試用版の **開始] をクリックします**。 

   ![イメージ of_Microsoft 365 E5 無料試用版ページを開始します。](../../media/mtp-eval-24.png)

3. 確認の基本設定を選択します。テキスト メッセージまたは通話を使用します。 決定したら、電話番号を入力し、選択内容に応じて[テキスト] または [電話] を選択します。

   ![イメージ of_Microsoft 365 E5 無料試用版ページを開始し、ロボットではないことを証明するコードを送信する連絡先の詳細を求める。](../../media/mtp-eval-25.png)
 
4. 確認コードを入力し、[無料試用版の **開始] をクリックします**。

   ![Image of_Microsoft 365 E5 無料試用版ページを開始し、システムが送信した検証コードを入力して、ロボットではないと証明できます。](../../media/mtp-eval-26.png)

5. [**今すぐ試す**] をクリックして、Microsoft 365 E5確認します。

   ![イメージ of_Microsoft 365 E5 [無料試用版を開始する] ページで、[今すぐ試す] ボタンを起動する必要があります。](../../media/mtp-eval-27.png)
 
6. [センター ユーザー]**の [Microsoft 365 管理アクティブ**  >  **ユーザー]**  >  **に移動します**。 ユーザー アカウントを選択し、[製品ライセンス **の管理]** を選択し、ライセンスを [ライセンス] から [Office 365 E5 Microsoft 365 E5。  **[保存]** をクリックします。

   ![イメージ of_Microsoft 365 管理センター ページで、ライセンスを選択Microsoft 365 E5できます。](../../media/mtp-eval-28.png)
 
7. グローバル管理者アカウントを再度選択し、[ユーザー名の管理 **] をクリックします**。

   ![[of_Microsoft 365 管理センター] ページで、[アカウント] を選択し、[ユーザー名の管理] を選択できます。](../../media/mtp-eval-29.png)

8. [省略可能]前 *の手順で* onmicrosoft.com に応じて、ドメインをドメインから独自のドメインに変更します。 **[変更の保存]** をクリックします。

   ![ドメインof_Microsoft変更できる 365 管理センター ページのイメージです。](../../media/mtp-eval-30.png)



## <a name="next-step"></a>次の手順
|[フェーズ 3: オンボードで&する](config-m365d-eval.md) | お客様のMicrosoft 365 Defenderラボまたはパイロット環境Microsoft 365 Defender、エンドポイントをオンボードする場合は、各デバイスの柱を構成します。
|:-------|:-----|
