---
title: Microsoft 365 Defender試用版ラボまたはパイロット環境を設定する
description: ポータルMicrosoft 365 Defenderアクセスし、Microsoft 365 Defender試用版ラボ環境を設定します
keywords: 試用版のセットアップMicrosoft 365 Defender、パイロットセットアップMicrosoft 365 Defender、Microsoft 365 Defenderを試す、評価ラボのセットアップをMicrosoft 365 Defenderする
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
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
- highpri
ms.topic: article
ms.openlocfilehash: 116efc949edace902b8e71abb27f5c091407fb14
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482276"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a>ラボ環境でMicrosoft 365 Defender試用版を設定する 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender 

このトピックでは、専用のラボ環境を設定する方法について説明します。 運用環境で試用版を設定する方法については、新しい[評価とパイロットMicrosoft 365 Defender](eval-overview.md)ガイドを参照してください。 

## <a name="create-an-office-365-e5-trial-tenant"></a>Office 365 E5試用版テナントを作成する
>[!NOTE]
>既に既存のOffice 365または Azure Active Directory サブスクリプションがある場合は、試用版テナントの作成手順Office 365 E5スキップできます。

1. [Office 365 E5製品ポータル](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)に移動し、[**無料試用版**] を選択します。

   :::image type="content" source="../../media/mtp-eval-9.png" alt-text="Office 365 E5無料試用版ページ" lightbox="../../media/mtp-eval-9.png":::
  
2. 電子メール アドレス (個人または企業) を入力して試用版の登録を完了します。 [ **アカウントの設定**] をクリックします。

   :::image type="content" source="../../media/mtp-eval-10.png" alt-text="Office 365 E5試用版登録のセットアップ ページ" lightbox="../../media/mtp-eval-10.png":::

3. 名、姓、勤務先の電話番号、会社名、会社の規模、国または地域を入力します。  

   :::image type="content" source="../../media/mtp-eval-11.png" alt-text="名前、電話、および会社の詳細を求めるOffice 365 E5試用版登録設定ページ" lightbox="../../media/mtp-eval-11.png":::
   
   > [!NOTE]
   > ここで設定した国またはリージョンによって、Office 365がホストされるデータ センターリージョンが決まります。
  
4. テキスト メッセージまたは通話を使用して、確認設定を選択します。 [ **確認コードの送信]** をクリックします。 

   :::image type="content" source="../../media/mtp-eval-12.png" alt-text="検証の設定を求めるOffice 365 E5試用版登録のセットアップ ページ" lightbox="../../media/mtp-eval-12.png":::

5. テナントのカスタム ドメイン名を設定し、[ **次へ**] をクリックします。

   :::image type="content" source="../../media/mtp-eval-13.png" alt-text="カスタム ドメイン名を設定できるOffice 365 E5試用版登録のセットアップ ページ" lightbox="../../media/mtp-eval-13.png":::
 
6. 最初の ID を設定します。これは、テナントのグローバル管理者になります。 名前と **パスワード** を入力 **します**。 [**サインアップ**] をクリックします。

   :::image type="content" source="../../media/mtp-eval-14.png" alt-text="ビジネス ID を設定できるOffice 365 E5試用版登録のセットアップ ページ" lightbox="../../media/mtp-eval-14.png":::

7. [**セットアップに移動]** をクリックして、Office 365 E5試用版テナント のプロビジョニングを完了します。

   :::image type="content" source="../../media/mtp-eval-15.png" alt-text="[セットアップに移動] ボタンをクリックするように求めるOffice 365 E5試用版登録のセットアップ ページ" lightbox="../../media/mtp-eval-15.png":::

8. 企業ドメインをOffice 365 テナントに接続します。 [省略可能] **[既に所有しているドメインを接続する** ] を選択し、ドメイン名を入力します。 **[次へ]** をクリックします。

   :::image type="content" source="../../media/mtp-eval-16.png" alt-text="サインインと電子メールをカスタマイズする必要がある [Office 365 E5セットアップ] ページ" lightbox="../../media/mtp-eval-16.png":::
 
9. TXT または MX レコードを追加して、ドメインの所有権を検証します。 TXT または MX レコードをドメインに追加したら、[ **確認**] を選択します。

   :::image type="content" source="../../media/mtp-eval-17.png" alt-text="ドメインを確認するために MX レコードの TXT を追加する必要があるOffice 365 E5セットアップ ページ" lightbox="../../media/mtp-eval-17.png":::
 
10. [省略可能]テナントのユーザー アカウントをさらに作成します。 [ **次へ**] をクリックすると、この手順をスキップできます。

    :::image type="content" source="../../media/mtp-eval-18.png" alt-text="ユーザーを追加できるOffice 365 E5セットアップ ページ" lightbox="../../media/mtp-eval-18.png":::
 
11. [省略可能]Office アプリをダウンロードします。 **[次へ**] をクリックして、この手順をスキップします。 

    :::image type="content" source="../../media/mtp-eval-19.png" alt-text="Office アプリをインストールできるOffice 365 E5 ページ" lightbox="../../media/mtp-eval-19.png":::

12. [省略可能]電子メール メッセージを移行します。 ここでも、この手順はスキップできます。

    :::image type="content" source="../../media/mtp-eval-20.png" alt-text="電子メール メッセージを移行するかどうかを設定できるOffice 365 E5" lightbox="../../media/mtp-eval-20.png":::
 
13. オンライン サービスを選択します。 **[Exchange**] を選択し、[**次へ**] をクリックします。 

    :::image type="content" source="../../media/mtp-eval-21.png" alt-text="オンライン サービスを選択できるOffice 365 E5" lightbox="../../media/mtp-eval-21.png":::

14. MX、CNAME、TXT レコードをドメインに追加します。 完了したら、[確認] を選択 **します**。

    :::image type="content" source="../../media/mtp-eval-22.png" alt-text="ここでは、DNS レコードを追加できるOffice 365 E5" lightbox="../../media/mtp-eval-22.png":::
 
15. おめでとうございます。Office 365 テナントのプロビジョニングが完了しました。

    :::image type="content" source="../../media/mtp-eval-23.png" alt-text="Office 365 E5セットアップ完了確認ページ" lightbox="../../media/mtp-eval-23.png":::
    

## <a name="enable-microsoft-365-trial-subscription"></a>Microsoft 365 試用版サブスクリプションを有効にする

>[!NOTE]
>試用版にサインアップすると、1 か月間使用する 25 個のユーザー ライセンスが提供されます。 詳細については、「 [Microsoft 365 サブスクリプションの試用または購入](../../commerce/try-or-buy-microsoft-365.md) 」を参照してください。

1. [Microsoft 365 管理 センター](https://admin.microsoft.com/)で [**課金**] をクリックし、[**サービスの購入]** に移動します。

2. **Microsoft 365 E5** を選択し、[**無料試用版の開始**] をクリックします。 

   :::image type="content" source="../../media/mtp-eval-24.png" alt-text="Microsoft 365 E5無料試用版の開始ページ" lightbox="../../media/mtp-eval-24.png":::

3. テキスト メッセージまたは通話を使用して、確認設定を選択します。 決定したら、電話番号を入力し、選択内容に応じて **[テキスト** ] または **[通話]** を選択します。

   :::image type="content" source="../../media/mtp-eval-25.png" alt-text="Microsoft 365 E5無料試用版の開始ページで、自分がロボットでないことを証明するコードを送信するための連絡先の詳細を求める" lightbox="../../media/mtp-eval-25.png":::
 
4. 確認コードを入力し、[ **無料試用版の開始]** をクリックします。

   :::image type="content" source="../../media/mtp-eval-26.png" alt-text="Microsoft 365 E5 無料試用版を開始するページで、システムから送信された検証コードに入力して、自分がロボットでないことを証明できます" lightbox="../../media/mtp-eval-26.png":::

5. [**今すぐ試す**] をクリックして、Microsoft 365 E5試用版を確認します。

   :::image type="content" source="../../media/mtp-eval-27.png" alt-text="Microsoft 365 E5[今すぐ試す] ボタンをクリックして開始する必要がある [無料試用版の開始] ページ" lightbox="../../media/mtp-eval-27.png":::
 
6. **Microsoft 365 管理 センター** > **ユーザー** > **アクティブ ユーザー** に移動します。 ユーザー アカウントを選択し、[**製品ライセンスの管理**] を選択し、ライセンスをOffice 365 E5から **Microsoft 365 E5** にスワップします。 **[保存]** をクリックします。

   :::image type="content" source="../../media/mtp-eval-28.png" alt-text="Microsoft 365 E5 ライセンスを選択できる [Microsoft 365 管理 センター] ページ" lightbox="../../media/mtp-eval-28.png":::
 
7. グローバル管理者アカウントをもう一度選択し、[ **ユーザー名の管理**] をクリックします。

   :::image type="content" source="../../media/mtp-eval-29.png" alt-text="[アカウント] と [ユーザー名の管理] を選択できる [Microsoft 365 管理 センター] ページ" lightbox="../../media/mtp-eval-29.png":::

8. [省略可能]前の手順で選択した内容に応じて、ドメインを *onmicrosoft.com* から独自のドメインに変更します。 **[変更の保存]** をクリックします。

   :::image type="content" source="../../media/mtp-eval-30.png" alt-text="ドメイン設定を変更できる [Microsoft 365 管理 センター] ページ" lightbox="../../media/mtp-eval-30.png":::

## <a name="next-step"></a>次のステップ
|[フェーズ 3: オンボード&構成する](config-m365d-eval.md) | Microsoft 365 Defender試用版ラボまたはパイロット環境の各Microsoft 365 Defenderの柱を構成し、エンドポイントをオンボードします。
|:-------|:-----|
