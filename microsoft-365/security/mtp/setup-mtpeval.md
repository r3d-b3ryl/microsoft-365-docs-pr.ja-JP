---
title: Microsoft の脅威保護の試用ラボまたはパイロット環境をセットアップする
description: Microsoft 365 セキュリティセンターにアクセスして、Microsoft の脅威保護のテスト環境をセットアップする
keywords: Microsoft Threat Protection 試用版のセットアップ、Microsoft Threat Protection パイロットセットアップ、microsoft threat protection、Microsoft Threat Protection 評価ラボの設定の試行
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a0997c107e78104619e1e05b8d1073e8690a3667
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195561"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a>Microsoft の脅威保護のテスト環境をセットアップする 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft Threat Protection 


Microsoft の脅威保護の試用ラボまたはパイロット環境を作成して展開するには、3つのフェーズがあります。

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Microsoft の脅威保護評価ラボまたはパイロット環境を準備する" />
      <br/>フェーズ 1: 準備 </a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Microsoft の脅威保護の試用ラボまたはパイロット環境をセットアップする" />
      <br/>フェーズ 2: セットアップ </a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab or pilot environment and onboard your endpoints" title="
Microsoft の脅威保護の試用ラボまたはパイロット環境とエンドポイントの各 Microsoft 脅威保護の柱を構成する" />
      <br/>フェーズ 3: 構成 & オンボード </a><br>
</td>


  </tr>
</table>

現在、セットアップ段階になっています。 最初の手順を実行して、Microsoft 365 セキュリティセンターにアクセスし、試用ラボまたはパイロット環境を設定します。

Microsoft 365 E5 ライセンスにサインアップするために使用できる onmicrosoft.com テナントを生成するには、Office 365 または Azure Active Directory サブスクリプションにサインアップし*ます。* 

>[!NOTE]
>既存の Office 365 または Azure Active Directory サブスクリプションを既に所有している場合は、「Office 365 E5 試用版またはパイロットのテナント作成の手順をスキップできます。

このフェーズでは、次の手順を実行します。
- Office 365 E5 試用版テナントを作成する
- Microsoft 365 試用版サブスクリプションを有効にする


## <a name="create-an-office-365-e5-trial-tenant"></a>Office 365 E5 試用版テナントを作成する
>[!NOTE]
>既存の Office 365 または Azure Active Directory サブスクリプションを既にお持ちの場合は、「Office 365 E5 試用版テナントの作成」の手順を省略できます。

1. [Office 365 E5 product ポータル](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)に移動し、**無料試用版**を選択します。
![イメージ of_Office 365 E5 無料試用版ページ](../../media/mtp-eval-9.png) <br>
  
2. メールアドレス (個人または企業) を入力して、試用版の登録を完了します。 [ **アカウントの設定] を**クリックします。
![Image of_Office 365 E5 試用版登録の設定ページ](../../media/mtp-eval-10.png) <br> 

3. 名、姓、勤務先電話番号、会社名、会社の規模、国または地域を入力します。  
<br>![Image of_Office 365 E5 試用版登録のセットアップページで、名前、電話番号、および会社の詳細を確認するページが表示されます。](../../media/mtp-eval-11.png) <br>
>[!NOTE]
>ここで設定した国または地域によって、Office 365 がホストされるデータセンターの地域が決まります。
  
4. 検証の設定: テキストメッセージまたは呼び出しを使用して選択します。 [ **送信確認コード**] をクリックします。 
![イメージ of_Office 365 E5 試用版の登録のセットアップページ確認の設定](../../media/mtp-eval-12.png) <br>

5. テナントのカスタムドメイン名を設定し、[ **次へ**] をクリックします。
<br>![イメージ of_Office 365 E5 試用版登録のセットアップページ。カスタムドメイン名を設定できます。](../../media/mtp-eval-13.png) <br>
 
6. 最初の id を設定します。これはテナントの全体管理者になります。 **名前**と**パスワード**を入力します。 **[サインアップ]** をクリックします。
![画像 of_Office 365 E5 試用版登録のセットアップページ。ビジネス id を設定できます。](../../media/mtp-eval-14.png) <br>

7. [ **セットアップに移動** ] をクリックして、Office 365 E5 試用版テナントのプロビジョニングを完了します。
<br>![Office のイメージ 365 E5 試用版の登録のセットアップページ [セットアップの開始] ボタンをクリックするように求める](../../media/mtp-eval-15.png) <br>

8. 会社のドメインを Office 365 テナントに接続します。 オプション[ **既に所有** しているドメインを接続する] を選択し、ドメイン名を入力します。 [**次へ**] をクリックします。
<br>![画像 of_Office 365 E5 セットアップページで、サインインとメールをカスタマイズする必要があります。](../../media/mtp-eval-16.png) <br>
 
9. TXT または MX レコードを追加して、ドメインの所有権を検証します。 ドメインに TXT または MX レコードを追加したら、[ **検証**] を選択します。
<br>![イメージ of_Office 365 E5 セットアップページ。ドメインを確認するために MX レコードの TXT を追加する必要があります。](../../media/mtp-eval-17.png) <br>
 
10. オプションテナントの追加のユーザーアカウントを作成します。 [ **次へ**] をクリックすると、この手順を省略できます。
![[イメージ of_Office 365 E5 セットアップ] ページで、さらにユーザーを追加できます。](../../media/mtp-eval-18.png) <br>
 
11. オプションOffice アプリをダウンロードします。 [ **次へ** ] をクリックして、この手順をスキップします。 
<br>![Office アプリをインストールできる Image of_Office 365 E5 ページ](../../media/mtp-eval-19.png) <br>

12. オプション電子メールメッセージを移行します。 この手順を省略してもかまいません。
<br>![画像 of_Office 365 E5 電子メールメッセージを移行するかどうかを設定するには](../../media/mtp-eval-20.png) <br>
 
13. [オンラインサービス] を選択します。 [ **Exchange** ] を選択し、[ **次へ**] をクリックします。 
<br>![画像 of_Office 365 E5 オンラインサービスを選択できます。](../../media/mtp-eval-21.png) <br>

14. MX、CNAME、および TXT レコードをドメインに追加します。 完了したら、[ **検証**] を選択します。
<br>![Image of_Office 365 E5 ここに DNS レコードを追加できます。](../../media/mtp-eval-22.png) <br>
 
15. おめでとうございます。 Office 365 テナントのプロビジョニングが完了しました。
<br>![Image of_Office 365 E5 セットアップ完了確認ページ](../../media/mtp-eval-23.png) <br>

## <a name="enable-microsoft-365-trial-subscription"></a>Microsoft 365 試用版サブスクリプションを有効にする

>[!NOTE]
>試用版にサインアップすると、1か月に使用する25ユーザーライセンスが提供されます。 詳細について [は、「Try Or Buy a M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) 」を参照してください。

1. [Microsoft 365 管理センター](https://admin.microsoft.com/)で、[**課金**] をクリックしてから [**購入サービス**] に移動します。

2. [ **Microsoft 365 E5** ] を選択し、[ **無料試用版の開始**] をクリックします。 
![Image of_Microsoft 365 E5 無料試用版ページ](../../media/mtp-eval-24.png) <br>

3. 検証の設定: テキストメッセージまたは呼び出しを使用して選択します。 決定したら、電話番号を入力し、選択した内容に応じて [ **自分のテキスト** を表示] または [ **呼び出し** ] を選択します。
![Image of_Microsoft 365 E5 無料試用版ページを開き、ロボットではないことを証明するコードを送信するための連絡先の詳細を確認します。](../../media/mtp-eval-25.png) <br>
 
4. 確認コードを入力して、[ **無料試用版の開始**] をクリックします。 
<br>![Image of_Microsoft 365 E5 Start free 試用版のページでは、システムが送信した検証コードに記入して、ロボットではないことを証明することができます。](../../media/mtp-eval-26.png) <br>

5. [ **今すぐ試行** ] をクリックして、Microsoft 365 E5 試用版を確認します。
<br>![Image of_Microsoft 365 E5 [無料試用版の開始] ページで、[今すぐ試行] ボタンを開始する必要があります。](../../media/mtp-eval-27.png) <br>
 
6. **Microsoft 365 管理センター**  >  **ユーザー**の  >  **アクティブユーザー**に移動します。 ユーザーアカウントを選択し、[ **製品ライセンスの管理**] を選択してから、ライセンスを Office 365 E5 から **Microsoft 365 e5**にスワップします。 [**保存**] をクリックします。
![Image of_Microsoft 365 管理センター] ページで、Microsoft 365 E5 ライセンスを選択できます。](../../media/mtp-eval-28.png) <br>
 
7. グローバル管理者アカウントをもう一度選択し、[ **ユーザー名の管理**] をクリックします。
<br>![Image of_Microsoft 365 管理センターページでは、アカウントを選択してから、ユーザー名を管理することができます。](../../media/mtp-eval-29.png) <br>

8. オプション前の手順で選択した内容に応じて、ドメインを *onmicrosoft.com* から独自のドメインに変更します。 **[変更の保存]** をクリックします。
<br>![イメージ of_Microsoft 365 管理センターページで、ドメインの設定を変更することができます。](../../media/mtp-eval-30.png) <br>



## <a name="next-step"></a>次のステップ
|![フェーズ 3: 構成 & オンボード](../../media/config-onboard.png) <br>[フェーズ 3: 構成 & オンボード](config-mtpeval.md) | Microsoft の脅威保護の試用ラボまたはパイロット環境とエンドポイントをオンボードにするために、Microsoft の各脅威保護の柱を構成します。
|:-------|:-----|
