---
title: エンドポイント検出用の Microsoft Defender を取得する Micro Focus ArcSight を構成する
description: Microsoft Defender セキュリティ センターから検出を受信およびプルする Micro Focus ArcSight を構成する
keywords: Micro Focus ArcSight、セキュリティ情報とイベント管理ツール、arcsight を構成する
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166187"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a>エンドポイント検出用の Defender をプルする Micro Focus ArcSight の構成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

エンドポイント検出用の Defender を取得するために、Micro Focus ArcSight を使用する一部のファイルとツールをインストールして構成する必要があります。

>[!Note]
>- [Defender for Endpoint Alert](alerts.md) は、1 つ以上の検出から構成されます。
>- [エンドポイント検出の Defender は](api-portal-mapping.md) 、デバイスで発生した疑わしいイベントとその関連するアラートの詳細から構成されます。

## <a name="before-you-begin"></a>はじめに

Micro Focus ArcSight Connector ツールを構成するには、Azure Active Directory (AAD) アプリケーションから検出をプルして解析するために、いくつかの構成ファイルが必要です。

このセクションでは、必要な構成ファイルを正しく設定して使用するために必要な情報を取得する方法について説明します。

- [設定] メニューから SIEM 統合機能を有効に **してください** 。 詳細については、「Defender [for Endpoint で SIEM 統合を有効にする」を参照してください](enable-siem-integration.md)。

- SIEM 統合機能を有効にしたファイルを準備します。 次の値を取得する必要があります。
  - OAuth 2.0 トークン更新 URL
  - OAuth 2.0 クライアント ID
  - OAuth 2.0 クライアント シークレット

- 次の構成ファイルを準備します。
  - WDATP-connector.properties
  - WDATP-connector.jsonparser.properties

    組織で使用する SIEM の種類として [Micro Focus ArcSight] を選択すると、これら 2 つのファイルを含む .zip ファイルが保存されているはずです。

- 次のトークンを生成し、準備ができていることを確認します。
  - アクセス トークン
  - refreshtoken

  これらのトークンは、ポータルの **SIEM 統合セットアップ** セクションから生成できます。

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a>Micro Focus ArcSight FlexConnector のインストールと構成

次の手順では、「開始する前に」で必要なすべての手順を完了 [したと仮定します](#before-you-begin)。

1. 最新の 32 ビット Windows FlexConnector インストーラーをインストールします。 この情報は、HPE ソフトウェア センターで確認できます。 ツールは通常、次の既定の場所にインストールされます `C:\Program Files\ArcSightFlexConnectors\current\bin` 。</br></br>ツールを保存する場所を選択できます (たとえば、C: \\ \current\bin folder_location\current\bin などfolder_location場所を表します。 

2. インストール ウィザードに従って、次のタスクを実行します。
   - 概要
   - [フォルダーのインストール] を選択する
   - [インストール セット] の選択
   - ショートカット フォルダーの選択
   - インストール前の概要
   - Installing...

   これらの各タスクの既定値を保持するか、要件に合わせて選択内容を変更できます。

3. エクスプローラーを開き、SIEM 統合機能を有効にした場合に保存した 2 つの構成ファイルを探します。 次に示す 2 つのファイルを FlexConnector のインストール場所に置く。

   - WDATP-connector.jsonparser.properties: C: folder_location \\ \current\user\agent\flexagent\

   - WDATP-connector.properties: C: folder_location \\ \current\user\agent\flexagent\

   > [!NOTE]
   > 
   > 構成ファイルは、この場所に置く必要があります *。folder_locationツールを* インストールした場所を表します。

4. コア コネクタのインストールが完了すると、[コネクタのセットアップ] ウィンドウが開きます。 [コネクタのセットアップ] ウィンドウで、[コネクタの **追加] を選択します**。

5. [種類: **ArcSight FlexConnector REST] を選択し、[次** へ] を **クリックします**。

6. パラメーターの詳細フォームに次の情報を入力します。 フォーム内の他のすべての値は省略可能で、空白のままにすることができます。

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th>フィールド</th>
    <th>値</th>
    </tr>
    <tr>
    <td>構成ファイル</td>
    <td>クライアント プロパティ ファイルの名前を入力します。 名前は、ダウンロードした .zip で指定されたファイルと一致している必要があります。
たとえば、flexagent ディレクトリの構成ファイルの名前がWDATP-Connector.jsonparser.properties の場合は、クライアント プロパティ ファイルの名前として &quot; &quot; &quot; &quot; &quot; WDATP-Connector と入力 &quot; する必要があります。</td>
    </tr>
    <td>イベント URL</td>
    <td>データセンターの場所に応じて、EU または米国の URL を選択します。 </br></br> <b>EU の</b>場合 : <i></i> https:// wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME <br>
   </br><b>米国の場合:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME <br> <br> <b>英国 :</b>https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</td>
    <tr>
    <td>認証の種類</td>
    <td>OAuth 2</td>
    </tr>
    <td>OAuth 2 クライアント プロパティ ファイル</td>
    <td><em>wdatp-connector.properties ファイルの場所を参照</em>します。 名前は、ダウンロードした .zip で指定されたファイルと一致している必要があります。</td>
    <tr>
    <td>更新トークン</td>
    <td>更新トークンは <b>、SIEM</b> 設定ページから更新トークンを生成するか、restutil ツールを使用する方法の 2 つの方法で取得できます。 <br><br> Preferences セットアップから更新トークンを生成する方法<b></b>の詳細については、「Defender for Endpoint で SIEM 統合を有効<a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">にする」を参照してください</a>。 </br> </br><b>restutil ツールを使用して更新トークンを取得します。</b> </br> a. コマンド プロンプトを開きます。 ツールをインストールした場所<em>folder_location\current\bin</em>folder_location C:\ に移動します。 <em></em> </br></br> b. Type: <code>arcsight restutil token -config</code> from the bin directory.たとえば <b>、arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> Web ブラウザー ウィンドウが開きます。 </br> </br>c. 資格情報を入力し、パスワード フィールドをクリックしてページをリダイレクトします。 ログイン プロンプトで、資格情報を入力します。 </br> </br>d. 更新トークンがコマンド プロンプトに表示されます。 </br></br> e. [トークンの更新] フィールドに <b>コピーして貼り付</b> けます。
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. コネクタによってブラウザー ウィンドウが開きます。 アプリケーション資格情報を使用してログインします。 ログイン後、OAuth2 クライアントにアクセス許可を与えるメッセージが表示されます。 コネクタ構成を認証するには、OAuth 2 クライアントにアクセス許可を与える必要があります。

   https <code>redirect_uri</code> URL の場合は、ローカル ホスト上の URL にリダイレクトされます。 ローカル ホストで実行されているコネクタによって提供される証明書を信頼する要求をするページが表示されます。 証明書が https の場合は、この証明書redirect_uri必要があります。
   
   ただし、証明書の http URL を指定redirect_uri、証明書の信頼に同意する必要はございません。

8. [Micro Focus ArcSight Connector Setup] ウィンドウに戻って、コネクタのセットアップを続行します。

9. 移動先 **として ArcSight Manager (暗号化)** を選択し、[次へ] を **クリックします**。

10. [マネージャーのホスト名] に宛先 IP/ホスト名を **入力** し、パラメーター フォームに資格情報を入力します。 フォーム内の他のすべての値は、既定値と一緒に保持する必要があります。 **[次へ]** をクリックします。

11. コネクタの詳細フォームにコネクタの名前を入力します。 フォーム内の他のすべての値は省略可能で、空白のままにすることができます。 **[次へ]** をクリックします。

12. ESM Manager インポート証明書ウィンドウが表示されます。 [証明書 **を宛先からコネクタにインポートする] を選択し、[** 次へ] を **クリックします**。 [ **コネクタの概要の追加]** ウィンドウが表示され、証明書がインポートされます。

13. [コネクタの概要の追加] ウィンドウの **詳細が正** しいか確認し、[次へ] を **クリックします**。

14. [サービス **としてインストール] を選択し、[** 次へ] を **クリックします**。

15. [サービスの内部名] **フィールドに名前を入力** します。 フォーム内の他のすべての値は、既定値または空白のままにして保持できます。 **[次へ]** をクリックします。

16. サービス パラメーターを入力し、[次へ] を **クリックします**。 [サービスの概要の **インストール] ウィンドウが** 表示されます。 **[次へ]** をクリックします。

17. [終了] と [次へ] を **選択してインストール** を **完了します**。

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a>Micro Focus ArcSight コンソールのインストールと構成

1. インストール ウィザードに従って、次のタスクを実行します。
   - 概要
   - 使用許諾契約書
   - 特別な通知
   - [ArcSight インストール ディレクトリの選択]
   - ショートカット フォルダーの選択
   - インストール前の概要

2. **[インストール]** をクリックします。 インストールが完了すると、ArcSight コンソール構成ウィザードが開きます。

3. [マネージャー のホスト名] **に「localhost」と入力し、[** マネージャー ポート] に「8443」 **と入力し、[次** へ] を **クリックします**。

4. [直接接続 **を使用する] を** 選択し、[次へ] を **クリックします**。

5. [パスワード **ベース認証] を選択** し、[次へ] を **クリックします**。

6. [これは **単一のユーザー インストールです] を選択します。(推奨) をクリック** し、[次へ] **をクリックします**。

7. [ **完了] を** クリックしてインストーラーを終了します。

8. Micro Focus ArcSight コンソールにログインします。

9. [アクティブ なチャネル **セット] [**  >  **新しい条件**  >  **デバイスデバイス製品]**  >  **に移動します**。

10. デバイス **製品を設定する = Microsoft Defender ATP**. イベントがツールに流れ込むのを確認した場合は、もう一度プロセスを停止して Windows Services に移動し、ArcSight FlexConnector REST を開始します。

これで、Micro Focus ArcSight コンソールでクエリを実行できます。

Defender for Endpoint detections は個別のイベントとして表示され、ベンダーは "Microsoft"、デバイス名は "Windows Defender ATP" として表示されます。


## <a name="troubleshooting-micro-focus-arcsight-connection"></a>Micro Focus ArcSight 接続のトラブルシューティング

**問題:** トークンの更新に失敗しました。 ログは、ツールをインストールした場所をfolder_location \\ \current\logs folder_location C: にあります。  _agent.log を開いて_ 探します `ERROR/FATAL/WARN` 。

**現象:** 次のエラー メッセージが表示されます。

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

**解決方法:**

1. [コネクタ] ウィンドウの [Ctrl ] + [C] をクリックして、プロセスを停止します。 「 **バッチ ジョブ Y/N** を終了する」というメッセージが表示された場合は、[Y] をクリックします。

2. WDATP-connector.properties ファイルを保存したフォルダーに移動し、編集して次の値を追加します `reauthenticate=true` 。

3. 次のコマンドを実行してコネクタを再起動します `arcsight.bat connectors` 。

   ブラウザー ウィンドウが表示されます。 実行を許可し、表示されなくなり、コネクタが実行されている必要があります。

> [!NOTE]
> もう一度プロセスを停止して、コネクタが実行されている状態を確認します。 次に、コネクタを再度起動すると、ブラウザー ウィンドウは表示されません。

## <a name="related-topics"></a>関連項目
- [Defender for Endpoint で SIEM 統合を有効にする](enable-siem-integration.md)
- [SIEM ツールへの検出のプル](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [REST API を使用したエンドポイント検出用の Defender のプル](pull-alerts-using-rest-api.md)
- [SIEM ツールの統合に関する問題のトラブルシューティング](troubleshoot-siem.md)
