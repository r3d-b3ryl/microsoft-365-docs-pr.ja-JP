---
title: Windows 365 Business PC とクラウド PC の使用を開始する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: 組織で Windows 365 Business を購入する方法と、ユーザーがクラウド PC の使用を開始する方法について学習します。
ms.openlocfilehash: 719faecdde15fbbcce7278cba414a7a4e2d94095
ms.sourcegitcommit: b3c4816b55657b87ed4a5f6a4abe3d505392218e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2021
ms.locfileid: "53726596"
---
# <a name="get-started-with-windows-365-business-and-cloud-pcs"></a>Windows 365 Business PC とクラウド PC の使用を開始する

この記事は、組織で Windows 365 Business を購入してセットアップする予定のユーザー向けです。 
  
[Windows 365 Business](https://www.microsoft.com/windows-365/business) は、小規模な企業 (最大 300 シート) で使用するために特別に作られた Windows 365 のバージョンです。 これにより、組織はクラウド PC をユーザーに提供する簡単で合理化された方法を提供できます。  Windows 365 クラウド PC を使用すると、Microsoft クラウドからアプリ、データ、コンテンツ、設定、ストレージをストリーミングできます。 

> [!NOTE]  
> 開始する前に、ユーザーの [Azure](/azure/active-directory/devices/device-management-azure-portal#configure-device-settings) ADデバイス設定が **[すべて**] に設定されている Azure ADに参加する可能性 **があります。** 

   ![ユーザーはデバイスを Azure ユーザー設定ADできます](../../media/deschutes/azure-device-settings.png)

## <a name="prerequisites"></a>前提条件
Windows 365 Business をセットアップするための前提条件はありません。


## <a name="buy-subscriptions"></a>サブスクリプションを購入する

ユーザー向け Windows 365 Business サブスクリプションを購入するには、次の 2 つの方法があります。
- [Windows 365 製品サイト](https://www.microsoft.com/windows-365/business/compare-plans-pricing)
- Microsoft 365 管理センター

サブスクリプションを購入した後、Microsoft 365 管理センターを使用して組織内のユーザーにライセンスを割り当てできます。 


### <a name="buy-subscriptions-through-the-windows-365-products-site"></a>Windows 365 製品サイトを通じてサブスクリプションを購入する

Microsoft 365 サブスクリプションをまだ持ってない場合は [、Windows 365](https://www.microsoft.com/windows-365/business/compare-plans-pricing)製品サイトで Windows 365 Business サブスクリプションを購入できます。 Windows 365 製品ページから Windows 365 Business サブスクリプションを購入するには、次の手順を使用します。   


1. [[Windows 365 Business] ページで、[](https://www.microsoft.com/windows-365/business)プランと価格 **を表示する] を選択します**。 
2. 次のページで、購入するサブスクリプションを選択し、[今すぐ購入] **を選択します**。
3. [Windows **365 Business の** 選択に感謝します] ページで、手順に従ってアカウントを設定します。
4. 手順 **5 - 確認** の詳細で、ユーザーにライセンスを割り当てる準備ができている場合は、[スタート] を選択して Windows 365 のホーム ページに移動します https://windows365.microsoft.com 。
5. Windows 365 ホーム ページの [クイック アクション] セクション **で、[組織** の管理 **] を選択します**。 これにより、Microsoft 365 管理センターにアクセスし、ユーザーにライセンスを割り当てできます。



### <a name="buy-a-subscription-through-the-microsoft-admin-center"></a>Microsoft 管理センターを通じてサブスクリプションを購入する

Microsoft 365 テナントが既に存在し、グローバル管理者または課金管理者である場合は、Microsoft 365 管理センターを使用して、組織の Windows 365 Business サブスクリプションを購入できます。

1. Microsoft 管理センターで、[サービスの購入] ページ **>に移動** します。
2. [サービス **の購入] ページ** で **、Windows 365 Business を検索します**。 見つけたら、[詳細] を **選択します**。
3. **[Windows 365 Business]** ページの [プロセッサ **/Ram/** ストレージ オプション] セクションで、[サブスクリプションの選択] メニューを使用して、CPU、RAM、およびストレージのニーズに基づいてユーザーのサブスクリプションを選択します。 ユーザーのニーズに最も適したサブスクリプションの選択に関するガイダンスについては [、「Windows 365 Business](windows-365-business-sizing.md) サイジング オプション」を参照してください。
4. [チェックアウト **] ページ** で、購入するサブスクリプションの数と支払い情報を入力します。 次に、[ **注文の配置] を選択します**。
5. **You'all set!** ページが表示され、購入の確認が表示されます。


## <a name="assign-licenses-to-users"></a>ユーザーにライセンスを割り当てる 

サブスクリプションを Windows 365 製品サイトから購入した場合でも、Microsoft 365 管理センターを通じて購入[](/microsoft-365/admin/manage/assign-licenses-to-users)した場合でも、Microsoft  365 管理センターの [課金] ページからユーザーにライセンスを割り当てできます。

ユーザーのビジネス上の必要に応じて、ユーザーに異なる Windows 365 Business ライセンスの種類を割り当てできます。 ユーザー [に適したライセンスの種類については、「Windows 365 Business](windows-365-business-sizing.md)  のサイズ変更オプション」をご覧ください。 


## <a name="get-your-users-started-with-cloud-pc"></a>ユーザーにクラウド PC の使用を開始する

ライセンスが割り当てられたら、クラウド PC にアクセスできる 2 つの異なる方法がユーザーに知らせることができます。

- Windows 365 のホーム ページ (https://windows365.microsoft.com)
- Microsoft リモート デスクトップ クライアントを使用する

### <a name="windows-365-home-page"></a>Windows 365 のホーム ページ

ユーザーは、自分の **https://windows365.microsoft.com** クラウド PC にアクセスするために移動できます。  

Windows 365 のホーム ページで、[クラウド PC] セクションにアクセスできるクラウド **PC が表示** されます。 

![Windows 365 ホーム](../../media/deschutes/cloudpc-home.png)

ユーザーは、[ブラウザーで **開く] を選択** してクラウド PC を開きます。

> [!NOTE]  
> モバイル デバイスは現在サポートされていません。

#### <a name="user-actions"></a>ユーザー操作

Windows 365 のホーム ページで、ユーザーはクラウド PC カードの歯車アイコンを選択して、クラウド PC でアクションを実行できます。

![カード メニュー](../../media/deschutes/cloudpc-gear.png)

- **再起動**: クラウド PC を再起動します。


- **リセット**: リセットは、次の手順を実行します。

    - Windows 10 を再インストールします。
    - 個人用ファイルを削除します。
    - 設定に加えた変更を削除します。
    - アプリを削除します。

    > [!IMPORTANT]  
    > クラウド PC をリセットする前に、クラウド ストレージ サービスまたは外部ストレージに保持する必要がある重要なファイルを必ずバックアップしてください。 クラウド PC をリセットすると、これらのファイルが削除されます。

- **名前** の変更 : Windows 365 ホーム ページでユーザーに表示されるクラウド PC の名前を変更します。 

- **トラブルシューティング**: ユーザーがクラウド PC に接続しない可能性がある問題のトラブルシューティングと修正を試みる。 次の表は、チェックによって発生する可能性がある状態を示しています。

    | 状態 | 説明 |
    |:-----|:-----|
    |問題が検出されない |どのチェックも、クラウド PC で問題を検出したのではありません。 |
    |解決された問題 |問題が検出され、修正されました。 |
    |クラウド PC に接続できません。 修正に取り組み、後でもう一度やり直します。 |接続に必要な Microsoft サービスは利用できません。 後でもう一度接続してみてください。 |
    |クラウド PC の問題を修正できません。 管理者に問い合わせてください。 |問題が検出されましたが、修正できません。 これは、継続的な Windows 更新プログラムまたは別の問題が原因である可能性があります。 このエラーが長い期間続く場合は、クラウド PC をリセットする必要があります。 |




### <a name="remote-desktop"></a>リモート デスクトップ

Microsoft リモート デスクトップ アプリを使用すると、ユーザーはクラウド PC を含むリモート PC にアクセスして制御できます。 Windows 365 ユーザーは、Windows 365 ホーム ページから必要なリモート デスクトップ クライアントをダウンロードしてインストールできます。 

#### <a name="install-the-microsoft-remote-desktop-app"></a>Microsoft リモート デスクトップ アプリのインストール

リモート デスクトップ クライアントをセットアップするには、次の手順を実行します。

1. Windows **365 ホーム ページで、Microsoft****リモート デスクトップ** アプリアイコン (ホーム アイコンの下) を選択します。 
2. [Microsoft **リモート デスクトップ アプリ] ページ** で、必要なリモート デスクトップ アプリをダウンロードしてインストールします。 

   ![リモート デスクトップ クライアント](../../media/deschutes/remote-desktop-apps.png)

オペレーティング システム別のクライアントの一覧については、「リモート デスクトップ [クライアント」を参照してください](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients)。 


## <a name="installing-apps"></a>アプリをインストールする

ユーザーは、アプリケーションの Web サイトからアプリをダウンロードするか、Microsoft Store からダウンロードすることで、通常は Windows の場合と同じ方法でアプリをクラウド PC にインストールできます。

すべての Windows 365 Business ユーザーは、クラウド PC でローカル管理者特権を持つ必要があります。そのため、アプリをワークスペースにインストールするために必要なアクセス許可が必要です。


 ## <a name="management-through-intune"></a>Intune による管理

Windows 365 Business では、プロビジョニング プロセスの一環として [クラウド PC](/mem/intune/fundamentals/what-is-intune) が Intune に登録されません。 組織とユーザーが適切にライセンスされている場合 [、Windows 10](/mem/intune/user-help/enroll-windows-10-device)コンピューターを Intune に登録する場合と同じ手順を使用して、クラウド PC を Intune に登録できます。

## <a name="how-to-get-help"></a>解決策の見つけ方

Microsoft 365 管理センターでの Windows 365 Business のセットアップ中にヘルプを受ける必要がある場合は、「ヘルプまたはサポートを受ける」 [を参照してください](/microsoft-365/business-video/get-help-support)。



## <a name="related-content"></a>関連コンテンツ

[Windows 365 Business](https://www.microsoft.com/windows-365/business) <br/>
[Windows 365 Business のサイズ設定オプション](windows-365-business-sizing.md) <br/>
[Windows 365 Business プランの比較](https://www.microsoft.com/windows-365/business/compare-plans-pricing) <br/>
[リモート デスクトップ クライアント アプリの比較](/windows-server/remote/remote-desktop-services/clients/remote-desktop-app-compare)<br/>
[小規模ビジネスMicrosoft Teamsを設定する](/microsoftteams/deploy-small-business)
