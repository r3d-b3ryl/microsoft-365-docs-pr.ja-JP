---
title: 管理者向け Application Guard for Office
keywords: アプリケーション ガード、保護、分離、分離コンテナー、ハードウェアの分離
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: ハードウェア ベースの分離の最新情報を取得します。 悪用や悪意のあるリンクのような現在および新しい攻撃が従業員の生産性と企業のセキュリティを妨げるのを防ぐ。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: da61ee2f5e29501e033ad44bc3fdb04ee2c042f0
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64473323"
---
# <a name="application-guard-for-office-for-admins"></a>管理者向け Application Guard for Office

**適用対象:** Word、Excel、および PowerPoint for Microsoft 365、Windows 10 Enterprise、Windows 11 Enterprise

Microsoft Defender Application Guard (Office 用 Application Office Guard) は、信頼されていないファイルが信頼できるリソースにアクセスし、企業が新しい攻撃や新たな攻撃から安全にアクセスするのを防ぐのに役立ちます。 この記事では、管理者が Application Guard for Office のプレビュー用にデバイスをセットアップする方法についてOffice。 デバイス上でアプリケーション ガードを有効にするためのシステム要件とインストール手順Office提供します。

## <a name="prerequisites"></a>前提条件

### <a name="minimum-hardware-requirements"></a>ハードウェアの最小要件

* **CPU**: 64 ビット、4 コア (物理または仮想)、仮想化拡張機能 (Intel VT-x OR AMD-V)、Core i5 同等以上の推奨
* **物理メモリ**: 8 GB RAM
* **ハード ディスク**: システム ドライブ上の 10 GB の空き領域 (SSD 推奨)

### <a name="minimum-software-requirements"></a>最小ソフトウェア要件

* **Windows**: Windows 10 Enterpriseバージョン 2004 (20H1) ビルド 19041 以降。 11 のWindowsがサポートされています。 
* **Office**: Office チャネルと月次 Enterprise チャネルのビルド バージョン 2011 16.0.13530.10000 以降。 Office Semi-Annual Enterprise、ビルド バージョン 2108 以降。 32 ビットバージョンと 64 ビット バージョンの両方のOfficeサポートされています。
* **更新プログラム パッケージ**: Windows 10月次セキュリティ更新 [プログラム KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

システム要件の詳細については、「システム要件」を参照[Microsoft Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)。 また、仮想化テクノロジを有効にする方法については、コンピューターの製造元のガイドを参照してください。
更新プログラム チャネルの詳細Office、更新プログラム チャネルの概要[を](/deployoffice/overview-update-channels)参照Microsoft 365。

### <a name="licensing-requirements"></a>ライセンスの要件

* Microsoft 365 E5またはMicrosoft 365 E5 Security

> [!NOTE]
> Microsoft 365 Apps for enterprise ベースのライセンスを使用している場合、アプリケーション のアプリケーション ガードにアクセスOffice。

## <a name="deploy-application-guard-for-office"></a>アプリケーションのアプリケーション ガードを展開Office

### <a name="enable-application-guard-for-office"></a>アプリケーションのアプリケーション ガードを有効Office

1. 累積的な毎月の **Windows 10 KB4571756 をダウンロードしてインストールします**。

2. [機能 **Microsoft Defender Application Guard] Windows** 選択し、[OK] を **選択します**。 Application Guard 機能を有効にすると、システムの再起動が促されます。 今すぐ再起動するか、手順 3 の後に再起動することを選択できます。

   :::image type="content" source="../../media/ag03-deploy.png" alt-text="AG Windows機能] ダイアログ ボックス" lightbox="../../media/ag03-deploy.png":::

   この機能は、管理者として次の PowerShell コマンドを実行して有効にすることもできます。

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. [管理モード **Microsoft Defender Application Guard、** コンピューター **構成\\Administrative テンプレート\\Windowsコンポーネント\\** Microsoft Defender Application Guard。 [オプション] の値を **2** または **3** に設定し、[OK] または [適用] を選択して、このポリシー **を** 有効 **にします**。

   :::image type="content" source="../../media/ag04-deploy.png" alt-text="管理モードで AG を有効にするオプション" lightbox="../../media/ag04-deploy.png":::

   代わりに、対応する CSP ポリシーを設定できます。

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/設定/AllowWindowsDefenderApplicationGuard** <br> データ型: **整数** <br> 値: **2**

4. システムを再起動します。

### <a name="set-diagnostics--feedback-to-send-full-data"></a>完全なデータ&送信する診断情報を設定する

> [!NOTE]
> ただし、これは必須ではありません。ただし、オプションの診断データを構成すると、報告された問題の診断に役立ちます。

この手順では、問題の特定と修正に必要なデータが Microsoft に届くという保証を行います。 次の手順に従って、デバイスで診断Windowsします。

1. [**設定** から開スタート メニュー。

   :::image type="content" source="../../media/ag05-diagnostic.png" alt-text="このスタート メニュー" lightbox="../../media/ag05-diagnostic.png":::

2. [プライバシー **Windows 設定**] を **選択します**。

   :::image type="content" source="../../media/ag06-diagnostic.png" alt-text="[Windows 設定] メニュー" lightbox="../../media/ag06-diagnostic.png":::

3. [プライバシー] の下で、[診断 **&] を選択し、[** オプションの診断 **データ] を選択します**。

   :::image type="content" source="../../media/ag07a-diagnostic.png" alt-text="[診断とフィードバック] メニュー" lightbox="../../media/ag07a-diagnostic.png":::

診断設定の構成Windows詳細については、「組織の診断[Windowsの構成」を参照してください](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)。

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>アプリケーションの Application Guard が有効Office動作を確認する

Application Guard for Officeが有効になっているか確認する前に、ポリシーが展開されているデバイスで Word、Excel、PowerPoint を起動します。 アクティブ化Office確認します。 作業 ID を使用して、最初に製品のライセンス認証Office場合があります。

アプリケーションの Application Guard が有効Office確認するには、Word、Excel、PowerPointを起動し、信頼されていないドキュメントを開きます。 たとえば、インターネットからダウンロードされたドキュメントや、組織外のユーザーからの電子メールの添付ファイルを開きます。

信頼されていないファイルを初めて開いた場合、次のOfficeのようなスプラッシュ画面が表示される場合があります。 アプリケーション のアプリケーション ガードがアクティブ化され、Office開いている間、しばらくの間表示される場合があります。 それ以降の信頼されていないファイルの開き方が速くなります。

:::image type="content" source="../../media/ag08-confirm.png" alt-text="[Office アプリスプラッシュ] ページ" lightbox="../../media/ag08-confirm.png":::

ファイルを開いた後、ファイルが Application Guard 内で開いているという視覚的なインジケーターが表示Office。

* リボンの吹き出し

  :::image type="content" source="../../media/ag09-confirm.png" alt-text="小さな App Guard メモを示す Doc ファイル" lightbox="../../media/ag09-confirm.png":::

* タスク バーにシールドが付くアプリケーション アイコン

  ![タスク バーのアイコン。](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>アプリケーション用に Application Guard を構成Office

Office次のポリシーをサポートして、アプリケーション のアプリケーション の機能を構成Office。 これらのポリシーは、グループ ポリシーまたはクラウド ポリシー サービスOffice[構成できます](/DeployOffice/overview-office-cloud-policy-service)。


> [!NOTE]
> これらのポリシーを構成すると、Application Guard で開いたファイルの一部の機能が無効Office。

|ポリシー|説明|
|---|---|
|アプリケーションに Application Guard を使用Office|このポリシーを有効にすると、Word、Excel、PowerPoint は、アプリケーション ガードの代わりに保護されたビュー分離コンテナーを使用Office。 このポリシーを使用すると、アプリケーションの有効な状態をOfficeに問題がある場合に、アプリケーション のアプリケーション ガードを一時的に無効Microsoft Edge。|
|コンテナーの事前作成Office Application Guard を構成する|このポリシーは、信頼されていないファイルを分離Office Application Guard for Office、実行時のパフォーマンスを向上するために事前に作成されるかどうかを決定します。 この設定を有効にした場合は、コンテナーの事前作成を続行する日数を指定するか、Office 組み込みのヒューリスティックでコンテナーを事前に作成できます。
|Application Guard で開いたドキュメントのコピー/貼りOffice貼り付けを許可Office|このポリシーを有効にすると、ユーザーは Application Guard で開いたドキュメントからコンテンツをコピーして貼り付け、Office開いたドキュメントに貼り付けできません。|
|アプリケーション のアプリケーション ガードでハードウェア アクセラレータを無効Office|このポリシーは、Application Guard for Officeアクセラレータを使用してグラフィックスをレンダリングするかどうかを制御します。 この設定を有効にすると、Application Guard for Office はソフトウェア ベース (CPU) レンダリングを使用し、サードパーティのグラフィックス ドライバーを読み込むか、接続されているグラフィックス ハードウェアを操作しません。
|Application Guard でサポートされていないファイルの種類の保護を無効Office|このポリシーは、Application Guard for Officeサポートされていないファイルの種類が開かれませんか、または保護されたビューへのリダイレクトを有効にするかどうかを制御します。
|Application Guard で開いたドキュメントのカメラとマイクへのアクセスをオフOffice|このポリシーを有効にすると、Officeの Application Guard 内のカメラとマイクへのアクセスがOffice。|
|Application Guard で開いたドキュメントからの印刷を制限Office|このポリシーを有効にすると、Application Guard で開いたファイルからユーザーが印刷できるプリンターが制限Office。 たとえば、このポリシーを使用して、ユーザーに PDF への印刷のみを制限できます。|
|ユーザーがファイルに対する保護のために Application Guard をOffice防ぐ|このポリシーを有効にすると、Office アプリケーション エクスペリエンス内で) オプションが削除され、Office 保護の Application Guard を無効にしたり、Application Guard for Office の外部でファイルを開くOffice。 <p> **注:** ユーザーは、ファイルから mark-of-the-web プロパティを手動で削除するか、ドキュメントを信頼できる場所に移動することによって、このポリシーをバイパスできます。|

> [!NOTE]
> 次のポリシーでは、ユーザーがサインアウトして再度サインインして、Windowsする必要があります。
>
> * アプリケーション のアプリケーション ガードで開いたドキュメントのコピー/貼り付けを無効Office
> * Application Guard で開いたドキュメントの印刷を制限Office
> * Application Guard で開いたドキュメントへのカメラとマイクのアクセスをオフOffice

## <a name="submit-feedback"></a>フィードバックの送信

### <a name="submit-feedback-via-feedback-hub"></a>フィードバック ハブ経由でフィードバックを送信する

Application Guard for Officeを起動するときに問題が発生した場合は、フィードバック ハブからフィードバックを送信してください。

1. フィードバック ハブ **アプリを開き** 、サインインします。

2. Application Guard の起動中にエラー ダイアログが表示される場合は、エラー ダイアログで **[Microsoft** に報告] を選択して、新しいフィードバックの送信を開始します。 それ以外の場合は、<https://aka.ms/mdagoffice-fb>Application Guard **+&nbsp;** の適切なカテゴリを選択し、[新しいフィードバックを追加する] を選択します。

3. [フィードバックの概要] ボックス **に** 、まだ入力されていない場合の概要を入力します。

4. [詳細な説明] ボックスに、発生した問題の詳細な説明と実行した手順を **入力** し、[次へ] を選択 **します**。

5. [問題] の横にあるバブルを **選択します**。 選択したカテゴリが [セキュリティ **\>** とプライバシー] Microsoft Defender Application Guard – Officeし、[次へ] を選択します。

6. [新 **しいフィードバック] を選択** し、[次へ] **を選択します**。

7. 問題に関するトレースを収集します。

   1. [自分の **問題の再作成] タイルを** 展開します。

   2. Application Guard の実行中に発生する問題が発生した場合は、Application Guard インスタンスを開きます。 インスタンスを開く場合、Application Guard コンテナー内から追加のトレースを収集できます。

   3. [ **記録の開始]** を選択し、タイルの回転が停止するのを待ち、[記録の停止] *と言います*。

   4. Application Guard の問題を完全に再現します。 再現には、Application Guard インスタンスを起動しようとして失敗するまで待機したり、実行中の Application Guard インスタンスで問題を再現したりすることがあります。

   5. [記録の **停止] タイルを選択** します。

   6. 送信後数分間でも、実行中の Application Guard インスタンスを開いた状態にしておき、コンテナー診断も収集できます。

8. 問題に関連するスクリーンショットやファイルを添付します。

9. **[送信]** を選択します。

### <a name="submit-feedback-via-office-customer-voice"></a>カスタマー ボイスからフィードバックOffice送信する

また、Application Guard でドキュメントを開いたOffice問題が発生した場合は、Officeからフィードバックを送信できます。 フィードバックの送信[については、「Officeインサイ](https://insider.office.com/handbook)ダー ハンドブック」を参照してください。

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>エンドポイント向け Microsoft Defender と Microsoft Defender との統合 (Office 365

Application Guard for Office Microsoft Defender for Endpoint と統合され、分離された環境で発生する悪意のあるアクティビティの監視とアラートを提供します。

[セーフ E365 E5](/microsoft-365/security/office-365-security/safe-docs) のドキュメントは、Microsoft Defender for Endpoint を使用して、Application Guard で開いたドキュメントをスキャンして、そのドキュメントをスキャンOffice。 保護の層を追加する場合、スキャンの結果が決定されるまで、ユーザーは Application Guard を離れOfficeアプリケーション ガードを終了できません。

Microsoft Defender for Endpoint は、エンタープライズ ネットワークが高度な脅威を防止、検出、調査、および対応するために設計されたセキュリティ プラットフォームです。 このプラットフォームの詳細については、「 [Microsoft Defender for Endpoint」を参照してください](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp)。 このプラットフォームへのデバイスのオンボーディングの詳細については、「 [デバイスを Microsoft Defender for Endpoint サービスにオンボードする」を参照してください](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。

また、Defender for Endpoint で動作Office 365 Microsoft Defender を構成できます。 詳細については、「Integrate [Defender for Office 365 Microsoft Defender for Endpoint」を参照してください](integrate-office-365-ti-with-mde.md)。

## <a name="limitations-and-considerations"></a>制限事項と考慮事項

* Application Guard for Office は、信頼されていないドキュメントを分離して、信頼できる企業リソース、イントラネット、ユーザーの ID、およびコンピューター上の任意のファイルにアクセスできない保護モードです。 その結果、ユーザーがディスク上のローカル ファイルから画像を挿入するなどのアクセスに依存する機能にアクセスしようとすると、アクセスは失敗し、次の例のようなプロンプトが表示されます。 信頼されていないドキュメントが信頼できるリソースにアクセスするには、ドキュメントから Application Guard 保護を削除する必要があります。 

  :::image type="content" source="../../media/ag09-confirm.png" alt-text="安全メッセージと機能の状態を示すダイアログ ボックス" lightbox="../../media/ag09-confirm.png":::

  > [!NOTE]
  > ユーザーに対して、ファイルとそのソースを信頼している場合、または保護元を信頼している場合にのみ、保護を削除する必要があります。

* 信頼されていないドキュメントが信頼できる場所に保存されている場合、その場所からの信頼はドキュメントによって継承されます。 通常、組織のクラウド ストレージは信頼できる場所として識別されます。
  
* マクロやコントロールのようなドキュメント内のアクティブ なActiveXは、アプリケーション ガードで無効Office。 アクティブ なコンテンツを有効にするには、Application Guard 保護を削除する必要があります。

* Application Guard で読み取り専用として開いている別の組織の OneDrive、OneDrive for Business、または SharePoint Online から共有されたネットワーク共有またはファイルからの信頼されていないファイル。 ユーザーは、そのようなファイルのローカル コピーを保存してコンテナー内で作業を続行したり、元のファイルを直接操作するために保護を削除することができます。

* Information Rights Management (IRM) によって保護されているファイルは、既定でブロックされます。 ユーザーが保護されたビューでこのようなファイルを開く場合、管理者は、組織のサポートされていないファイルの種類のポリシー設定を構成する必要があります。

* Application Guard for OfficeアプリケーションをOfficeカスタマイズしても、ユーザーがサインアウトして再度サインインした後、またはデバイスが再起動した後も保持されません。

* UIA フレームワークを使用するアクセシビリティ ツールのみ、アプリケーション ガードで開いたファイルに対してアクセス可能なエクスペリエンスを提供Office。

* インストール後に Application Guard を最初に起動するには、ネットワーク接続が必要です。 Application Guard がライセンスを検証するには、接続が必要です。

* ドキュメントの情報セクションでは、Last *Modified By* プロパティに **WDAGUtilityAccount** がユーザーとして表示される場合があります。 WDAGUtilityAccount は、Application Guard で構成された匿名ユーザーです。 デスクトップ ユーザーの ID は Application Guard コンテナー内で共有されていない。

## <a name="performance-optimizations-for-application-guard-for-office"></a>アプリケーション用 Application Guard のパフォーマンスOffice

このセクションでは、Application Guard で使用されるパフォーマンスの最適化の概要をOffice。 この情報は、Application Guard が有効な場合に、管理者がシステムまたはシステム全体Officeパフォーマンスに関連するユーザーからのレポートを診断するのに役立ちます。

Application Guard は仮想化コンテナーを使用して、信頼されていないドキュメントをシステムから分離します。 コンテナーを作成し、Application Guard コンテナーをセットアップして Office ドキュメントを開くプロセスでは、パフォーマンスのオーバーヘッドが発生し、ユーザーが信頼できないドキュメントを開く際のユーザー エクスペリエンスに悪影響を及ぼす可能性があります。

必要なファイルを開くエクスペリエンスをユーザーに提供するために、Application Guard はロジックを使用して、システムで次のヒューリスティックが満たされている場合にコンテナーを事前に作成します。ユーザーが過去 28 日間に保護ビューまたは Application Guard でファイルを開いた。

このヒューリスティックが満たされた場合、Officeユーザーがユーザーにサインインした後、ユーザーの Application Guard コンテナーを事前に作成Windows。 この事前作成操作の進行中に、システムのパフォーマンスが低下する可能性がありますが、操作が完了するとすぐに効果が解決されます。

> [!NOTE]
> ヒューリスティックがコンテナーを事前に作成するために必要なヒントは、ユーザーがコンテナーを使用Officeアプリケーションによって生成されます。 ユーザーが Application Guard が有効になっている新しいシステムに Office をインストールした場合、Office は、ユーザーがシステムで信頼されていないドキュメントを初めて開くまで、コンテナーを事前に作成しません。 ユーザーは、この最初のファイルが Application Guard で開くのに時間がかかるのを確認します。

## <a name="known-issues"></a>既知の問題

* Web リンク ( または ) を`http` 選択 `https`しても、ブラウザーは開かれません。
* コピー貼り付け保護ポリシーの既定の設定では、テキストへのクリップボード アクセスのみを有効にします。
* サポートされていないファイルの種類保護ポリシーの既定の設定は、暗号化されている、または Information Rights Management (IRM) が設定されている、信頼されていないサポートされていないファイルの種類を開くのをブロックすることです。 これには、暗号化を使用して機密ラベルMicrosoft Information Protectionするファイル (機密または機密性の高いファイル) が含まれます。
* 現時点では、CSV ファイルと HTML ファイルはサポートされていません。
* 現在、NTFS Officeの Application Guard は動作しません。 "エラー" が表示される場合は、ERROR_VIRTUAL_DISK_LIMITATIONの圧縮を解除してください。
* .NET を更新すると、Application Guard でファイルが開かない場合があります。 回避策として、ユーザーは、このエラーが発生した場合にデバイスを再起動できます。 問題の詳細については、「サンドボックスを開く際にエラー メッセージを受け取Windows Defender Application Guard[またはWindowsしてください](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)。
* 詳細については[、「よく寄せられる質問 - Microsoft Defender Application Guard」を参照してください。](/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard) 
