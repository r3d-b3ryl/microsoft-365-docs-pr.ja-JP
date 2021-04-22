---
title: Microsoft 365 Defender 試用版ラボまたはパイロット環境をセットアップする
description: Access Microsoft 365 Security Center その後、Microsoft 365 Defender 試用版ラボ環境をセットアップする
keywords: Microsoft 365 Defender 試用版セットアップ、Microsoft 365 Defender パイロット セットアップ、Microsoft 365 Defender、Microsoft 365 Defender 評価ラボセットアップを試す
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae81f6be0a83d5d0141f0f0c8c89f8f2207cc56c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935427"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Microsoft 365 Defender 試用版ラボ環境のセットアップ 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender 


Microsoft 365 Defender 試用版ラボまたはパイロット環境を作成し、それを展開するには、次の 3 段階のプロセスを実行します。

|[![フェーズ 1: 準備](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)<br/>[フェーズ 1: 準備](prepare-m365d-eval.md) |![フェーズ 2: 設定](../../media/phase-diagrams/setup.png)<br/>フェーズ 2: 設定 |[![フェーズ 3: オンボード](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)<br/>[フェーズ 3: オンボード](config-m365d-eval.md) | [![パイロットに戻る](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[パイロット プレイブックに戻る](m365d-pilot.md) |
|--|--|--|--|
||*お前はここにいる!*  | | |


現在、セットアップ フェーズに入っている。 最初の手順を実行して Microsoft 365 セキュリティ センターにアクセスし、試用版ラボまたはパイロット環境をセットアップします。

Office 365 または Azure Active Directory サブスクリプションにサインアップして、Microsoft 365 E5 ライセンスにサインアップするために使用できる *.onmicrosoft.com* テナントを生成します。 

>[!NOTE]
>既存の 365 または Azure Active Directory サブスクリプションOfficeしている場合は、Office 365 E5 試用版またはパイロット テナントの作成手順をスキップできます。

このフェーズでは、次の情報に案内されます。
- 365 E5 Officeテナントを作成する
- Microsoft 365 試用版サブスクリプションを有効にする


## <a name="create-an-office-365-e5-trial-tenant"></a>365 E5 Officeテナントを作成する
>[!NOTE]
>既存のサブスクリプション 365 または Azure Active Directory サブスクリプションOfficeしている場合は、365 E5 試用版テナントの作成手順Officeスキップできます。

1. [365 E5 Officeに](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)移動し、[無料試用版]**を選択します**。

   ![Image of_Office 365 E5 無料試用版ページ](../../media/mtp-eval-9.png)
  
2. 電子メール アドレス (個人または企業) を入力して、試用版の登録を完了します。 [アカウント **の設定] をクリックします**。

   ![Image of_Office 365 E5 試用版登録のセットアップ ページ](../../media/mtp-eval-10.png)

3. 名、名、会社の電話番号、会社名、会社の規模、国または地域を入力します。  

   ![名前、電話Office会社の詳細を求める画像 of_Office 365 E5 試用版登録セットアップ ページ](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > ここで設定した国または地域によって、365 のデータ センター Officeが決定されます。
  
4. 確認の基本設定を選択します。テキスト メッセージまたは通話を使用します。 [検証 **コードの送信] をクリックします**。 

   ![検証の設定をOfficeする Image of_Office 365 E5 試用版登録セットアップ ページ](../../media/mtp-eval-12.png)

5. テナントのカスタム ドメイン名を設定し、[次へ] を **クリックします**。

   ![Image of_Office 365 E5 試用版登録セットアップ ページ (カスタム ドメイン名を設定できる)](../../media/mtp-eval-13.png)
 
6. テナントのグローバル管理者になる最初の ID を設定します。 [名前] **と [パスワード]** を **入力します**。 **[サインアップ]** をクリックします。

   ![ビジネス ID をOfficeできる Image of_Office 365 E5 試用版登録セットアップ ページ](../../media/mtp-eval-14.png)

7. [ **セットアップに移動] を** クリックして、Office 365 E5 試用版テナントのプロビジョニングを完了します。

   ![[Go setup] Officeをクリックするように求める 365 E5 試用版登録セットアップ ページのイメージ](../../media/mtp-eval-15.png)

8. 企業ドメインを 365 テナントOffice接続します。 [省略可能][ **既に所有しているドメインを接続する] を選択し** 、ドメイン名を入力します。 [ **次へ**] をクリックします。

   ![サインインとメールOfficeカスタマイズする必要がある 365 E5 セットアップ ページの画像](../../media/mtp-eval-16.png)
 
9. TXT レコードまたは MX レコードを追加して、ドメインの所有権を検証します。 ドメインに TXT レコードまたは MX レコードを追加したら、[確認] を **選択します**。

   ![ドメインを確認Office MX レコードの TXT を追加する必要がある Image of_Office 365 E5 セットアップ ページ](../../media/mtp-eval-17.png)
 
10. [省略可能]テナントのユーザー アカウントを作成します。 [次へ] をクリックすると、この手順を **スキップできます**。

    ![Image of_Officeユーザーを追加できる 365 E5 セットアップ ページ](../../media/mtp-eval-18.png)
 
11. [省略可能]アプリOfficeダウンロードします。 [次 **へ] を** クリックして、この手順をスキップします。 

    ![Image of_Office 365 E5 ページで、アプリをインストールOfficeできます](../../media/mtp-eval-19.png)

12. [省略可能]電子メール メッセージを移行します。 繰り返しますが、この手順は省略できます。

    ![Image of_Office 365 E5 電子メール メッセージを移行するかどうかを設定できます](../../media/mtp-eval-20.png)
 
13. [オンライン サービス] を選択します。 **[Exchange] を選択し**、[次へ]**をクリックします**。 

    ![オンライン サービスをOfficeできる Image of_Office 365 E5](../../media/mtp-eval-21.png)

14. ドメインに MX、CNAME、TXT レコードを追加します。 完了したら、[確認] を **選択します**。

    ![Image of_Office 365 E5 HERE では、DNS レコードを追加できます](../../media/mtp-eval-22.png)
 
15. おめでとうございます、365 テナントのプロビジョニングOffice完了です。

    ![Image of_Office 365 E5 セットアップ完了確認ページ](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Microsoft 365 試用版サブスクリプションを有効にする

>[!NOTE]
>試用版にサインアップすると、1 か月間 25 のユーザー ライセンスを使用できます。 詳細 [については、「Try or Buy a M365 サブスクリプション」](../../commerce/try-or-buy-microsoft-365.md) を参照してください。

1. [Microsoft 365 管理センターで、[課金](https://admin.microsoft.com/)**]** をクリックし、[サービスの購入]**に移動します**。

2. [Microsoft **365 E5] を選択し、[** 無料試用版の開始 **] をクリックします**。 

   ![イメージ of_Microsoft 365 E5 無料試用版の開始ページ](../../media/mtp-eval-24.png)

3. 確認の基本設定を選択します。テキスト メッセージまたは通話を使用します。 決定したら、電話番号を入力し、選択内容に応じて[テキスト] または [電話] を選択します。

   ![Image of_Microsoft 365 E5 無料試用版ページを開始して、ロボットではないことを証明するコードを送信する連絡先の詳細を求める](../../media/mtp-eval-25.png)
 
4. 確認コードを入力し、[無料試用版の **開始] をクリックします**。

   ![Image of_Microsoft 365 E5 無料試用版ページを開始して、システムが送信した検証コードを入力して、ロボットではないと証明できます](../../media/mtp-eval-26.png)

5. [ **今すぐ試す** ] をクリックして、Microsoft 365 E5 試用版を確認します。

   ![Image of_Microsoft 365 E5 無料試用版ページを開始するには、[今すぐ試す] ボタンを起動する必要があります。](../../media/mtp-eval-27.png)
 
6. **[Microsoft 365 管理センター ユーザー] [アクティブ**  >  **ユーザー**  >  **] に移動します**。 ユーザー アカウントを選択し、[製品ライセンスの **管理**] を選択し、ライセンスを 365 E5 Office **Microsoft 365 E5 に交換します**。 **[保存]** をクリックします。

   ![[of_Microsoft 365 管理センター] ページで、Microsoft 365 E5 ライセンスを選択できます。](../../media/mtp-eval-28.png)
 
7. グローバル管理者アカウントを再度選択し、[ユーザー名の管理 **] をクリックします**。

   ![[of_Microsoft 365 管理センター] ページで[アカウント] を選択し、[ユーザー名の管理] を選択できます。](../../media/mtp-eval-29.png)

8. [省略可能]前 *の手順で* onmicrosoft.com に応じて、ドメインをドメインから独自のドメインに変更します。 **[変更の保存]** をクリックします。

   ![ドメインof_Microsoft変更できる 365 管理センター ページのイメージ](../../media/mtp-eval-30.png)



## <a name="next-step"></a>次の手順
|[フェーズ 3: オンボードで&する](config-m365d-eval.md) | Microsoft 365 Defender 試用版ラボまたはパイロット環境用に各 Microsoft 365 Defender の柱を構成し、エンドポイントをオンボードします。
|:-------|:-----|
