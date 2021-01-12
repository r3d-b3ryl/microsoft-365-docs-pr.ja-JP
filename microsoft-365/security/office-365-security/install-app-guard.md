---
title: Application Guard for Office 365 (パブリック プレビュー) (管理者向け)
keywords: application guard, 保護, 分離, 分離コンテナー, ハードウェアの分離
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 最新のハードウェア ベースの分離を取得します。 悪用や悪意のあるリンクなど、現在および新たな攻撃が従業員の生産性や企業のセキュリティを妨害するのを防ぐ。
ms.openlocfilehash: f5a5feb14db75c5baccecf0c6afafe0c42517224
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794510"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a>Application Guard for Office (パブリック プレビュー) (管理者向け)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**適用対象:** Word、Excel、PowerPoint for Microsoft 365、Windows 10 Enterprise

> [!IMPORTANT]
> 一部の情報は、リリース前の製品に関連します。製品が商用リリースされる前に大幅に変更される可能性があります。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft Defender Application Guard for Office (Office 用 Application Guard) は、信頼されていないファイルが信頼できるリソースにアクセスし、新たな攻撃から企業を安全に保護するのに役立ちます。 この記事では、管理者が Application Guard for Office のプレビュー用にデバイスをセットアップする方法についてOffice。 システム要件とインストール手順に関する情報を提供し、デバイスで Application Guard Officeを有効にします。

## <a name="prerequisites"></a>前提条件

### <a name="minimum-hardware-requirements"></a>ハードウェアの最小要件

* **CPU**: 64 ビット、4 コア (物理または仮想)、仮想化拡張機能 (Intel VT-x または AMD-V)、Core i5 と同等以上の推奨
* **物理メモリ**: 8 GB RAM
* **ハード ディスク**: システム ドライブに 10 GB の空き領域 (SSD を推奨)

### <a name="minimum-software-requirements"></a>最小ソフトウェア要件

* **Windows 10**: Windows 10 Enterprise エディション、クライアント ビルド バージョン 2004 (20H1) ビルド 19041
* **Office**: Office Beta Channel Build バージョン 2008 16.0.13212 以降
* **更新プログラム パッケージ**: Windows 10 の累積的な月次セキュリティ更新 [プログラム KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

システム要件の詳細については、「Microsoft Defender Application Guard のシステム要件」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)。 Insider Preview ビルドのOffice詳細については、「Insider ビルドの展開の概要 [Office参照してください](https://insider.office.com/business/deploy)。

### <a name="licensing-requirements"></a>ライセンスの要件

* Microsoft 365 E5 または Microsoft 365 E5 セキュリティ

## <a name="deploy-application-guard-for-office"></a>Application Guard を展開してOffice

### <a name="enable-application-guard-for-office"></a>アプリケーションの Application Guard を有効Office

1. Windows 10 の累積的な月次セキュリティ更新プログラム **KB4571756 をダウンロードしてインストールします**。

2. Windows の **機能で Microsoft Defender Application Guard** を選択し **、[OK] を選択します**。 Application Guard 機能を有効にすると、システムの再起動を求めるメッセージが表示されます。 今すぐ再起動するか、手順 3. の後で再起動することを選択できます。

   ![AG を示す [Windows の機能] ダイアログ ボックス](../../media/ag03-deploy.png)

   この機能は、管理者として次の PowerShell コマンドを実行して有効にすることもできます。

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. コンピューターの構成管理用テンプレート Windows コンポーネント Microsoft Defender Application Guard にある管理モードグループ ポリシーで **Microsoft Defender Application Guard \\ \\ \\ を探します**。 [オプション] の値を **2** または **3** に設定し **、[OK]** または [適用] を選択して、このポリシーを有効 **にします**。

   ![管理モードで AG を有効にする](../../media/ag04-deploy.png)

   または、対応する CSP ポリシーを設定できます。

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> データ型: **整数** <br> 値: **2**

4. システムを再起動します。

### <a name="set-diagnostics--feedback-to-send-full-data"></a>完全なデータ&送信する診断データのフィードバックを設定する

この手順により、問題の特定と修正に必要なデータが Microsoft に到達することを保証します。 Windows デバイスで診断を有効にするには、次の手順を実行します。

1. スタート **メニューから [** 設定] を開きます。

   ![[スタート] メニュー](../../media/ag05-diagnostic.png)

2. **[Windows の設定] で、[** プライバシー] を **選択します**。

   ![[Windows の設定] メニュー](../../media/ag06-diagnostic.png)

3. [プライバシー] で、フィードバック **に対して [&] を選択し** 、[オプションの診断 **データ] を選択します**。

   ![[診断とフィードバック] メニュー](../../media/ag07a-diagnostic.png)

Windows 診断設定の構成の詳細については、「組織内での Windows 診断データの [構成」を参照してください](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)。

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>アプリケーションの Application Guard が有効Office機能を確認する

Application Guard for Office が有効になっているか確認する前に、ポリシーが展開されているデバイスで Word、Excel、または PowerPoint を起動します。 アクティブ化Office確認します。 作業 ID を使用して、最初に製品のライセンス認証Office必要な場合があります。

Application Guard for Officeが有効にされたのを確認するには、Word、Excel、または PowerPoint を起動し、信頼されていないドキュメントを開きます。 たとえば、インターネットからダウンロードしたドキュメントや、組織外のユーザーからの電子メールの添付ファイルを開きます。

信頼されていないファイルを最初に起動すると、次のようなOfficeスプラッシュ画面が表示される場合があります。 Application Guard for Officeがアクティブ化され、ファイルが開いている間、しばらくの間表示される場合があります。 それ以降の信頼されていないファイルの起動は、より高速である必要があります。

![Officeスプラッシュ画面](../../media/ag08-confirm.png)

ファイルを開いた後、ファイルが Application Guard 内でファイルを開いたという視覚的なインジケーターが表示Office。

* リボン内の吹き出し

  ![小さな App Guard のメモを示すドキュメント ファイル](../../media/ag09-confirm.png)

* タスク バーに盾が表示されたアプリケーション アイコン

  ![タスク バーのアイコン](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>アプリケーション用に Application Guard をOffice

Office次のポリシーをサポートし、アプリケーションの Application Guard の機能を構成Office。 これらのポリシーは、グループ ポリシーまたはクラウド ポリシー サービスOffice構成できます。

> [!NOTE]
> これらのポリシーは間もなく使用可能になります。
> また、これらのポリシーを構成すると、アプリケーション の Application Guard で開いたファイルの一部の機能Office。

|ポリシー|説明|
|---|---|
|アプリケーションの Application Guard を無効Office|このポリシーを有効にすると、Word、Excel、および PowerPoint は、Application Guard for Office の代わりに保護ビュー分離コンテナーを使用する必要があります。 このポリシーを使用すると、Edge で Application Guard を有効Office問題がある場合に、アプリケーション の Application Guard を一時的に無効にできます。|
|Application Guard で開いたドキュメントのコピー/貼り付けを無効にする|このポリシーを有効にすると、Application Guard for Office で開いたドキュメントから、外部で開いたドキュメントにコンテンツをコピーして貼り付けできません。|
|ユーザーがファイルに対する Application Guard 保護を削除する|このポリシーを有効にすると、(Office アプリケーション エクスペリエンス内で) Application Guard 保護を無効にするか、Application Guard の外部でファイルを開くオプションが削除されます。 <p> **注:** このポリシーは、ファイルから手動で削除するか、ドキュメントを信頼できる場所に移動することでバイパスできます。|
|Application Guard で開いたドキュメントからの印刷を制限する|このポリシーを有効にすると、ユーザーが Application Guard で開いたファイルから印刷できるプリンターがOffice。 たとえば、このポリシーを使用して、ユーザーが PDF にのみ印刷できるよう制限できます。|
|Application Guard で開いたドキュメントのカメラとマイクへのアクセスをオフにする|このポリシーを有効にすると、Officeの Application Guard 内のカメラとマイクへのアクセスがOffice。|
|

> [!NOTE]
> 次のポリシーを有効にするには、ユーザーがログオフして Windows に再ログインする必要があります。
>
> * Application Guard で開いたドキュメントのコピー/貼り付けを無効にする
> * Application Guard で開いたドキュメントの印刷を制限する
> * Application Guard で開いたドキュメントへのカメラとマイクのアクセスをオフにする

## <a name="submit-feedback"></a>フィードバックの送信

### <a name="submit-feedback-via-feedback-hub"></a>フィードバック Hub 経由でフィードバックを送信する

Application Guard for Office を起動するときに問題が発生した場合は、フィードバック Hub からフィードバックを送信してください。

1. フィードバック Hub **アプリを開き** 、サインインします。

2. Application Guard の起動中にエラー ダイアログが表示された場合は、エラー ダイアログで **[Microsoft** に報告] を選択して、新しいフィードバックの送信を開始します。 それ以外の場合は、Application Guard の適切なカテゴリを選択するために移動し、+[新しいフィードバックの追加] を右 <https://aka.ms/mdagoffice-fb> に選択します。 

3. まだ入力 **されていない場合は、[** フィードバックの要約] ボックスに入力します。

4. 発生した **問題と** 実行した手順の詳細な説明を [詳細に説明] ボックスに入力し、[次へ] を選択 **します**。

5. 問題の横にあるバブルを選択します。 選択したカテゴリがセキュリティとプライバシーに関する Microsoft Defender Application Guard Officeし、[ **\> 次へ**] を選択 **します**。

6. [新 **しいフィードバック] を選択し**、[次へ] **を選択します**。

7. 問題に関するトレースを収集します。

   1. [問題 **の再作成] タイルを展開** します。

   2. Application Guard の実行中に問題が発生した場合は、Application Guard インスタンスを開きます。 これにより、Application Guard コンテナー内から追加のトレースを収集できます。

   3. [Start **recording] (** レコーディングの開始) を選び、タイルの回転が止まるのを待ち、[記録を停止] と *言います*。

   4. Application Guard の問題を完全に再現します。 これには、Application Guard インスタンスを起動しようとして失敗するまで待機したり、実行中の Application Guard インスタンスで問題を再現したりすることがあります。

   5. [記録の **停止] タイルを選択** します。

   6. 実行中の Application Guard インスタンスは、申請の数分後まで開いた状態にしておき、コンテナー診断も収集できます。

8. 問題に関連するスクリーンショットやファイルを添付します。

9. **[送信]** を選択します。

### <a name="submit-feedback-via-office-customer-voice"></a>カスタマー ボイスを使用してOfficeを送信する

また、Application Guard でドキュメントを開Office問題が発生した場合は、Officeからフィードバックを送信できます。 フィードバックの提出 [についてはOffice Insider ハンド](https://insider.office.com/handbook) ブックを参照してください。

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Microsoft Defender for Endpoint および Microsoft Defender for Office 365 との統合

Application Guard for Office Microsoft Defender for Endpoint と統合され、分離された環境で発生する悪意のあるアクティビティの監視と警告を提供します。

Microsoft Defender for Endpoint は、エンタープライズ ネットワークが高度な脅威を防止、検出、調査、および対応するために設計されたセキュリティ プラットフォームです。 このプラットフォームについて詳しくは [、Microsoft Defender for Endpoint のページをご覧](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) ください。 このプラットフォームへのデバイスのオンボードについて詳しくは、デバイスを Microsoft Defender for Endpoint サービス [にオンボードする方法をご覧ください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。

また、Office 365 用に Microsoft Defender をエンドポイント用の Defender と組み合Office構成できます。 「Microsoft [Defender for Endpoint と Office 365 の Defender の統合」をご覧ください](integrate-office-365-ti-with-wdatp.md)。

## <a name="limitations-and-considerations"></a>制限事項と考慮事項

* Office 用 Application Guard は、信頼できる企業リソース、イントラネット、ユーザーの ID、およびコンピューターに存在する任意のファイルへの信頼されていないドキュメントのアクセスを分離する制限付きモードです。 その結果、たとえばディスク上のローカル ファイルから画像を挿入するなどのアクセスに依存する機能にユーザーがアクセスしようとすると、エラーが発生し、次のようなプロンプトが表示されます。 信頼されていないドキュメントが信頼できるリソースにアクセスするには、ユーザーがドキュメントから Application Guard 保護を削除する必要があります。

  ![[安全に保つために、この機能は使用できません] というダイアログ ボックス](../../media/ag10-limitations.png)

  > [!NOTE]
  > ファイルとそのソース、またはファイルの送信元を信頼している場合にのみ、保護を削除する必要があります。

* Application Guard では、マクロやコントロールActiveXドキュメント内のアクティブなコンテンツが無効Office。 アクティブなコンテンツを有効にするには、Application Guard 保護を削除する必要があります。

* ネットワーク共有から開いた信頼できないファイルや、別の組織の OneDrive、OneDrive for Business、または SharePoint Online から共有されたファイルは、Application Guard で読み取り専用として開きます。 ユーザーは、そのようなファイルのローカル コピーを保存してコンテナー内で作業を続行したり、元のファイルを直接操作する保護を削除することができます。

* Information Rights Management (IRM) によって保護されているファイルは、引き続き保護ビューで開きます。

* Application Guard for Office アプリケーションをOfficeしたカスタマイズは、ユーザーがログオフしてデバイスにログインまたは再起動した後も保持されません。

* UIA フレームワークを使うアクセシビリティ ツールだけが、アプリ用 Application Guard で開いたファイルにアクセシビリティ対応のエクスペリエンスOffice。

* インストール後に Application Guard を初めて起動するには、ネットワーク接続が必要です。 これは、Application Guard がライセンスを検証するために必要です。

* ドキュメントの情報セクションでは、 *最終* 変更者プロパティにユーザーとして WDAGUtilityAccount が表示される場合があります。 デスクトップ ユーザーの ID が Application Guard コンテナー内で共有されていない場合、これは Application Guard で構成された匿名ユーザーです。

## <a name="performance-optimizations-for-application-guard"></a>Application Guard のパフォーマンスの最適化

このセクションでは、Application Guard で使用されるパフォーマンスの最適化の概要をOffice。 この情報は、Application Guard が有効な場合に、管理者が Office またはシステム全体のパフォーマンスに関連するユーザーからのレポートを診断するのに役立ちます。

Application Guard は、仮想化されたコンテナーを使用して、信頼されていないドキュメントをシステムから分離します。 コンテナーを作成し、application Guard コンテナーを設定して Office ドキュメントを開くプロセスでは、パフォーマンスのオーバーヘッドが発生し、ユーザーが信頼されていないドキュメントを開く際のユーザー エクスペリエンスに悪影響を及ぼす可能性があります。

ユーザーに期待されるファイルを開くエクスペリエンスを提供するために、Application Guard はロジックを使用して、システムで次のヒューリスティックが満たされた場合にコンテナーを事前に作成します。ユーザーが過去 28 日間に保護ビューまたは Application Guard でファイルを開いている。

このヒューリスティックが満たされたOffice、ユーザーが Windows にログインした後に、ユーザーの Application Guard コンテナーが事前に作成されます。 この作成前操作が進行中の場合、システムのパフォーマンスが低下する可能性があります。 これは、操作が完了するとすぐに解決されます。

> [!NOTE]
> コンテナーの事前作成に使用されるヒューリスティックに必要なヒントは、ユーザーがコンテナーを使用するOfficeアプリケーションによって生成されます。 Application Guard が有効になっている新しいシステムに Office をインストールした場合、Office は、ユーザーがシステム上で信頼されていないドキュメントを初めて開くまでコンテナーを事前に作成しません。 ユーザーは、この最初のファイルが Application Guard で開くのに時間がかかるのを確認します。

## <a name="known-issues-in-preview"></a>プレビューでの既知の問題

* Web リンク (または) をクリック `http` `https` しても、ブラウザーは開かれません。
* .NET 更新プログラムを実行すると、Application Guard でファイルが開かれません。 回避策として、この問題が発生した場合、ユーザーはデバイスを再起動できます。 Application Guard または Windows サンドボックスを開こうとすると、エラー メッセージを受信するWindows Defender [詳細を確認してください](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)。
