---
title: Microsoft 365 Defender 試用版ラボまたはパイロット環境をセットアップする
description: Microsoft 365 セキュリティ センターにアクセスし、Microsoft 365 Defender 試用版ラボ環境をセットアップする
keywords: Microsoft Threat Protection 試用版のセットアップ, Microsoft Threat Protection パイロット セットアップ, Microsoft Threat Protection, Microsoft Threat Protection 評価ラボのセットアップ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932984"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Microsoft 365 Defender 試用版ラボ環境をセットアップする 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender 


Microsoft 365 Defender 試用版ラボまたはパイロット環境を作成して展開するには、次の 3 段階のプロセスがあります。

|[![フェーズ 1: 準備](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[フェーズ 1: 準備](prepare-mtpeval.md) |![フェーズ 2: セットアップ](../../media/phase-diagrams/setup.png)<br/>フェーズ 2: セットアップ |[![フェーズ 3: オンボーディング](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[フェーズ 3: オンボーディング](config-mtpeval.md) | [![パイロットに戻る](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[パイロット プレイブックに戻る](mtp-pilot.md) |
|--|--|--|--|
||*ここにいます。*  | | |


現在セットアップ フェーズ中です。 最初の手順を実行して Microsoft 365 セキュリティ センターにアクセスし、試用版ラボまたはパイロット環境を設定します。

Office 365 または Azure Active Directory サブスクリプションにサインアップして、Microsoft 365 E5 ライセンスへのサインアップに使用できる *.onmicrosoft.com* テナントを生成します。 

>[!NOTE]
>既存の Office 365 または Azure Active Directory サブスクリプションがある場合は、Office 365 E5 試用版またはパイロット テナント作成手順をスキップできます。

このフェーズでは、次のガイドが表示されます。
- Office 365 E5 試用版テナントを作成する
- Microsoft 365 試用版サブスクリプションを有効にする


## <a name="create-an-office-365-e5-trial-tenant"></a>Office 365 E5 試用版テナントを作成する
>[!NOTE]
>既存の Office 365 または Azure Active Directory サブスクリプションがある場合は、Office 365 E5 試用版テナントの作成手順を省略できます。

1. [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)製品ポータルに移動し、[無料試用版]**を選択します**。

   ![Image of_Office 365 E5 free trial page](../../media/mtp-eval-9.png)
  
2. メール アドレス (個人または企業) を入力して、試用版の登録を完了します。 [アカウント **の設定] をクリックします**。

   ![Image of_Office 365 E5 trial registration setup page](../../media/mtp-eval-10.png)

3. 名、名、名、会社の電話番号、会社名、会社の規模、国または地域を入力します。  

   ![名前、電話Office会社の詳細を求める_Office 365 E5 試用版登録のセットアップ ページの画像](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > ここで設定する国または地域によって、Office 365 がホストされるデータ センターの地域が決なります。
  
4. 確認の基本設定を選択します。テキスト メッセージまたは通話を使用します。 [確認 **コードの送信] をクリックします**。 

   ![検証のOfficeを求める_Office 365 E5 試用版登録のセットアップ ページの画像](../../media/mtp-eval-12.png)

5. テナントのカスタム ドメイン名を設定し、[次へ] をクリック **します**。

   ![カスタム ドメイン名Office設定できる_Office 365 E5 試用版登録のセットアップ ページの画像](../../media/mtp-eval-13.png)
 
6. テナントのグローバル管理者になる最初の ID を設定します。 名前と **パスワードを** 入力 **します**。 **[サインアップ]** をクリックします。

   ![ビジネス ID をOfficeできる_Office 365 E5 試用版登録のセットアップ ページの画像](../../media/mtp-eval-14.png)

7. [ **セットアップに移動] を** クリックして、Office 365 E5 試用版テナントのプロビジョニングを完了します。

   ![[Go Setup] Officeをクリックするように求める 365 E5 試用版登録のセットアップ ページの画像](../../media/mtp-eval-15.png)

8. 企業ドメインを Office 365 テナントに接続します。 [省略可能]Choose **Connect a domain you already own** and type in your domain name. [**次へ**] をクリックします。

   ![サインインとメールOfficeカスタマイズする必要がある_Office 365 E5 セットアップ ページの画像](../../media/mtp-eval-16.png)
 
9. TXT レコードまたは MX レコードを追加して、ドメインの所有権を検証します。 ドメインに TXT レコードまたは MX レコードを追加したら、[確認] を選択 **します**。

   ![ドメインを確認Office MX レコードの TXT を追加する必要がある_Office 365 E5 セットアップ ページの画像](../../media/mtp-eval-17.png)
 
10. [省略可能]テナント用にさらにユーザー アカウントを作成します。 You can skip this step by clicking **Next**.

    ![ユーザーを追加Officeできる_Office 365 E5 セットアップ ページの画像](../../media/mtp-eval-18.png)
 
11. [省略可能]アプリOfficeダウンロードします。 [ **次へ] を** クリックしてこの手順をスキップします。 

    ![アプリをOfficeできる_Office 365 E5 ページOffice画像](../../media/mtp-eval-19.png)

12. [省略可能]電子メール メッセージを移行します。 繰り返しになりますが、この手順は省略できます。

    ![電子メール Officeするかどうかを設定できる_Office 365 E5 の画像](../../media/mtp-eval-20.png)
 
13. オンライン サービスを選択します。 **[Exchange] を選択し**、[次へ] を **クリックします**。 

    ![オンライン サービスをOfficeできる_Office 365 E5 の画像](../../media/mtp-eval-21.png)

14. MX、CNAME、TXT レコードをドメインに追加します。 完了したら、[確認] を **選択します**。

    ![DNS レコードを追加Office_Office 365 E5 の画像](../../media/mtp-eval-22.png)
 
15. これで完了です。365 テナントのプロビジョニングOffice完了です。

    ![Image of_Office 365 E5 setup completion confirmation page](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Microsoft 365 試用版サブスクリプションを有効にする

>[!NOTE]
>試用版にサインアップすると、1 か月間使用できる 25 のユーザー ライセンスが提供されます。 詳細 [については、「M365 サブスクリプションを試用または購入する](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) 」を参照してください。

1. [Microsoft 365 管理センターで、[](https://admin.microsoft.com/)**課金]** をクリックし、[サービスの購入]**に移動します**。

2. **Microsoft 365 E5 を選択し、[** 無料試用版の開始]**をクリックします**。 

   ![Image of_Microsoft 365 E5 Start free trial page](../../media/mtp-eval-24.png)

3. 確認の基本設定を選択します。テキスト メッセージまたは通話を使用します。 決定したら、電話番号を入力し、選択内容に応じて[自分にテキスト] または [電話] を選択します。

   ![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)
 
4. 確認コードを入力し、[無料試用版 **の開始] をクリックします**。

   ![Image of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)

5. Click **Try now** to confirm your Microsoft 365 E5 trial.

   ![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)
 
6. Go to the **Microsoft 365 Admin Center** Users  >  **Active**  >  **users**. ユーザー アカウントを選択し、[製品ライセンスの管理] を選択し、ライセンスを Office 365 E5 から **Microsoft 365 E5 に交換します**。 **[保存]** をクリックします。

   ![[Of_Microsoft 365 管理センター] ページで Microsoft 365 E5 ライセンスを選択できる画像](../../media/mtp-eval-28.png)
 
7. グローバル管理者アカウントを再び選択し、[ユーザー名の管理] **をクリックします**。

   ![Image of_Microsoft 365 Admin Center page where you can select Account and then Manage username](../../media/mtp-eval-29.png)

8. [省略可能]前の手順で *onmicrosoft.com* に応じて、ドメインをドメインから独自のドメインに変更します。 **[変更の保存]** をクリックします。

   ![ドメインof_Microsoft変更できる [365 管理センター] ページの画像](../../media/mtp-eval-30.png)



## <a name="next-step"></a>次の手順
|[フェーズ 3: オンボードの&する](config-mtpeval.md) | Microsoft 365 Defender 試用版ラボまたはパイロット環境用に各 Microsoft 365 Defender の柱を構成し、エンドポイントをオンボードします。
|:-------|:-----|
