---
title: Microsoft Managed Desktop の構成可能な設定リファレンス
description: Microsoft Managed Desktop で構成可能な設定のカテゴリを設定する
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 33347a6dc42183d4ffa1b1e069fd93f63099bdee
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034607"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>構成可能な設定リファレンス - Microsoft Managed Desktop

このトピックでは、Microsoft Managed Desktop で構成できる設定カテゴリの一覧を示します。 各設定カテゴリには、要件、ベスト プラクティス、設定カテゴリのカスタマイズ方法に関する情報が含まれます。 

## <a name="desktop-background-picture"></a>デスクトップの背景画像
組織内の Microsoft Managed Desktop デバイスのデスクトップの背景画像をカスタマイズできます。 これを使用して、会社のブランドまたはマーケティング 資料を適用できます。 

### <a name="requirements"></a>要件

デスクトップの背景画像では、次の要件を満たす必要があります。
- ピクチャ ファイル形式 - .jpg、jpeg、または .png
- ファイルの場所 - 信頼できるセキュリティで保護された http (https) の場所でホストします。 
- 許可されていません - Http とファイル共有 (unc) の場所はサポートされていません。 

### <a name="customize-and-deploy-desktop-background-picture"></a>デスクトップの背景画像をカスタマイズして展開する

**カスタム デスクトップの背景画像を追加するには**
1. サインインして [デバイス [Microsoft エンドポイント マネージャー]](https://endpoint.microsoft.com/)メニュー **に移動** します。
2. [Microsoft 管理デスクトップ] セクションを探し、[デスクトップ] を **設定。**
3. [**デスクトップ設定]** で、[デスクトップの **背景画像] を選択します**。 
4. 使用する画像の場所を入力します。 
5. [ **ステージ展開] を** 選択して変更を保存し、テスト グループに展開します。 

## <a name="browser-start-pages"></a>ブラウザーの開始ページ
ブラウザーのスタート ページは、ユーザーがページを開始するときに個々のタブMicrosoft Edge。 ユーザーが頻繁に使用する一連のサイトを簡単に開く場合は、サイトごとにブラウザーの開始ページを追加します。 

### <a name="requirements"></a>要件

ブラウザーのスタート ページにイントラネットまたはインターネット サイトの完全修飾ドメイン名 (FQDN) を指定する必要があります。 内部サイトが構成されている場合、これらのサイトへのアクセスは、社内ネットワークに接続されている場合、または VPN 接続に接続されている場合にのみ許可されていることをユーザーに知らせて下さい。 

### <a name="customize-and-deploy-browser-start-pages"></a>ブラウザーの開始ページのカスタマイズと展開

**ブラウザーの開始ページを追加するには**
1. サインインして [デバイス [Microsoft エンドポイント マネージャー]](https://endpoint.microsoft.com/)メニュー **に移動** します。
2. [Microsoft 管理デスクトップ] セクションを探し、[デスクトップ] を **設定。**
3. [**ブラウザー設定]** ワークスペースで、[ブラウザーの **開始ページ] を選択します**。 
4. [スタート **ページの追加] を選択します**。
5. [ **ブラウザーの開始ページの追加]** で、使用するサイトの URL を入力し、[スタート ページの追加 **] を選択します**。 
6. 追加のブラウザーの開始ページについては、手順 1 ~ 5 を繰り返します。 
7. [ **ステージ展開] を** 選択して変更を保存し、テスト グループに展開します。

## <a name="enterprise-mode-site-list-location"></a>Enterprise モードのサイト一覧の場所

Microsoft Edge との互換性に問題がある特定の Web サイトやアプリがある場合は、Enterprise モード サイト一覧を使用して、Internet Explorer 11 を使用して web サイトを自動的に開きます。 また、イントラネット サイトが Microsoft Edge で正しく動作しない場合は、すべてのイントラネット サイトを 11 を使用して自動的に開Internet Explorerできます。 [Enterprise モードを使用すると、Microsoft Edgeブラウザーとして引き続き使用できる一方で、アプリが 11 で引き続き動作Internet Explorerします。 エンタープライズ モード サイト一覧の詳細については、「Enterprise モードと Enterprise[リスト」を参照してください](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)。 

エンタープライズ モード サイト一覧 https:// ホストしている内部共有の場所、または場所を指定できます。 

### <a name="requirements"></a>要件

エンタープライズ モードのサイト 一覧ファイルでは、次の要件を満たす必要があります。
- ファイル形式 - ファイル要件を満たす [XML ファイル](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- ファイルの場所 - 内部 https の場所にファイルをホストします。 
- 許可されない - *//sharename* のような内部ファイル共有でのホスティングは許可されません

### <a name="best-practices"></a>ベスト プラクティス

これらのベスト プラクティスは、お客様が IT インフラストラクチャの最新化を決定する上で役立ちます。
- **限られた数** のサイトを選択します。 Microsoft Managed Desktop では、組織の全体的なセキュリティとユーザーの使いやすさを向上させるために、Microsoft Edgeを優先ブラウザーとして使用します。 この一覧のほとんどのサイトは、古いバージョンのブラウザーを必要とする従来の Web アプリ向けで、多くのセキュリティ機能が含まれます。 
- **別のサイトを検討** する – 古いブラウザーを必要としない別のサイトまたは Web アプリを検討してください。 または、新しいブラウザーを使用できるようサイトを更新する方法を検討してください。 新しいブラウザーは最新のテクノロジを使用し、セキュリティの向上に役立ちます。

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>サイト モードの一Enterprise場所をカスタマイズして展開する

**エンタープライズ サイト モードの一覧の場所を追加するには**

1. サインインして [デバイス [Microsoft エンドポイント マネージャー]](https://endpoint.microsoft.com/)メニュー **に移動** します。
2. [Microsoft 管理デスクトップ] セクションを探し、[デスクトップ] を **設定。**
3. **[設定]** ワークスペースで、[サイト 一 **覧Enterpriseの場所] を選択します**。 
4. サイト一覧の https の場所を入力します。 
5. [ **ステージ展開] を** 選択して変更を保存し、テスト グループに展開します。

## <a name="trusted-sites"></a>信頼済みサイト

信頼済みサイトを使用すると、さまざまなサイトのセキュリティ ゾーンやサイトを使用できる場所をカスタマイズできます。 セキュリティ ゾーンには、次のものが含まれます。 
- ゾーン 1 – ローカル イントラネット ゾーン
- ゾーン 2 – 信頼済みサイト ゾーン
- ゾーン 3 – インターネット ゾーン
- ゾーン 4 – 制限付きサイト ゾーン

### <a name="requirements"></a>要件

信頼済みサイトごとにイントラネットまたはインターネット サイトの完全修飾ドメイン名 (FQDN) を指定します。 

### <a name="customize-and-deploy-trusted-sites"></a>信頼できるサイトのカスタマイズと展開

**信頼できるサイトを追加するには**

1. サインインして [デバイス [Microsoft エンドポイント マネージャー]](https://endpoint.microsoft.com/)メニュー **に移動** します。
2. [Microsoft 管理デスクトップ] セクションを探し、[デスクトップ] を **設定。**
3. **[設定]** ワークスペースで、[信頼済 **みサイト] を** 選択し、[信頼済みサイトの **追加] を選択します**。 
4. [ **信頼済みサイトの追加**] で、URL を入力し、セキュリティ ゾーンを選択し、[信頼済みサイトの追加 **] を選択します**。 
5. 追加する信頼済みサイトごとに手順 1 ~ 4 を繰り返します。 
6. [ **ステージ展開] を** 選択して変更を保存し、テスト グループに展開します。

**信頼できるサイトを削除するには**

1. サインインして [デバイス [Microsoft エンドポイント マネージャー]](https://endpoint.microsoft.com/)メニュー **に移動** します。
2. [Microsoft 管理デスクトップ] セクションを探し、[デスクトップ] を **設定。**
3. [信頼 **設定]** ワークスペースで、[信頼済みサイト]**を選択します**。 
4. 削除するサイトを選択し、[削除] を **選択します**。 
5. 削除する信頼済みサイトごとに手順 1 ~ 4 を繰り返します。 
6. [ **ステージ展開] を** 選択して変更を保存し、テスト グループに展開します。

## <a name="proxy"></a>プロキシ
組織のネットワーク プロキシ設定を管理できます。 プロキシ サーバーとポート番号を追加し、プロキシ サイトの例外を追加します。 Microsoft Managed Desktop には、サービスを動作するために必要な一連の既定のプロキシ例外が含まれています。 既定の除外リストは、Microsoft Managed Desktop サービスによってのみ変更できます。  詳細については [、「Microsoft Managed Desktop のネットワーク構成」を参照してください](../get-ready/network.md)。 

Microsoft Managed Desktop ポータルに追加するプロキシ サイトの例外は、Microsoft Managed Desktop サービスに含まれる既定のプロキシ例外に追加されます。 

> [!NOTE]
> 既定のプロキシ例外リストの更新は、常に顧客の展開よりも優先されます。 つまり、既定のプロキシ例外リストの展開がある場合、ステージ展開は一時停止されます。  

### <a name="requirements"></a>要件

プロキシ サーバーとプロキシ サイトの例外に対して、次の要件を満たす必要があります。
- 有効なサーバー アドレスとポート番号である必要があります
- URL は有効な http サイトである必要があります 

### <a name="customize-and-deploy-proxies"></a>プロキシのカスタマイズと展開

**個々のプロキシ サイトの例外を追加するには**

1. サインインして [デバイス [Microsoft エンドポイント マネージャー]](https://endpoint.microsoft.com/)メニュー **に移動** します。
2. [Microsoft 管理デスクトップ] セクションを探し、[デスクトップ] を **設定。**
3. [設定] ワークスペース **で**、[プロキシ] を **選択します**。 
4. プロキシ サーバー **のアドレス** と **ポート番号** を入力し、[プロキシ例外の追加 **] を選択します**。 
5. 有効な http サイトの URL を入力し、[プロキシ例外の追加 **] を選択します**。 
6. 追加する信頼済みサイトごとに手順 1 ~ 5 を繰り返します。 
7. [ **ステージ展開] を** 選択して変更を保存し、テスト グループに展開します。

## <a name="additional-resources"></a>その他のリソース
- [構成可能な設定の概要](config-setting-overview.md) 
- [構成可能な設定を展開する](config-setting-deploy.md)