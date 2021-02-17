---
title: Application Guard for Office 365 for admins
keywords: application guard, 保護, 分離, 分離コンテナー, ハードウェアの分離
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 最新のハードウェア ベースの分離を取得します。 悪用や悪意のあるリンクなど、現在および新たな攻撃が従業員の生産性や企業のセキュリティを妨害するのを防ぐ。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 50065c4c0b9cbac9dee29892d9ebb0c7ce5f20f8
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261527"
---
# <a name="application-guard-for-office-for-admins"></a>管理者向け Application Guard for Office

**適用対象:** Word、Excel、PowerPoint for Microsoft 365、Windows 10 Enterprise

Microsoft Defender Application Guard for Office (Office 用 Application Guard) は、信頼されていないファイルが信頼できるリソースにアクセスし、新たな攻撃から企業を安全に保護するのに役立ちます。 この記事では、管理者が Application Guard for Office のプレビュー用にデバイスをセットアップする方法についてOffice。 システム要件とインストール手順に関する情報を提供し、デバイスで Application Guard Officeを有効にします。

## <a name="prerequisites"></a>前提条件

### <a name="minimum-hardware-requirements"></a>ハードウェアの最小要件

* **CPU**: 64 ビット、4 コア (物理または仮想)、仮想化拡張機能 (Intel VT-x または AMD-V)、Core i5 と同等以上の推奨
* **物理メモリ**: 8 GB RAM
* **ハード ディスク**: システム ドライブに 10 GB の空き領域 (SSD を推奨)

### <a name="minimum-software-requirements"></a>最小ソフトウェア要件

* **Windows 10**: Windows 10 Enterprise エディション、クライアント ビルド バージョン 2004 (20H1) ビルド 19041 以降
* **Office**: Office Current Channel Build Version 2011 16.0.13530.10000 以降。 32 ビットバージョンと 64 ビット バージョンの両方のOfficeサポートされています。
* **更新プログラム パッケージ**: Windows 10 の累積的な月次セキュリティ更新 [プログラム KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

システム要件の詳細については、「Microsoft Defender Application Guard のシステム要件」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)。 更新プログラム チャネルの詳細Office Microsoft [365](https://docs.microsoft.com/deployoffice/overview-update-channels)の更新プログラム チャネルの概要を参照してください。

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

3. 管理モード **で Microsoft Defender Application Guard を検索** します。グループ ポリシーは、[コンピューターの構成管理用テンプレート **] Windows \\ \\ コンポーネントの Microsoft Defender Application Guard \\ です**。 [オプション] の値を **2** または **3** に設定し **、[OK]** または [適用] を選択して、このポリシーを有効 **にします**。

   ![管理モードで AG を有効にする](../../media/ag04-deploy.png)

   代わりに、対応する CSP ポリシーを設定できます。

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> データ型:**整数** 型 <br> 値: **2**

4. システムを再起動します。

### <a name="set-diagnostics--feedback-to-send-full-data"></a>完全なデータ&送信する診断機能のフィードバックを設定する

この手順により、問題の特定と修正に必要なデータが Microsoft に到達することを保証します。 Windows デバイスで診断を有効にするには、次の手順を実行します。

1. スタート **メニューから [** 設定] を開きます。

   ![[スタート] メニュー](../../media/ag05-diagnostic.png)

2. **[Windows の設定] で、[** プライバシー] を **選択します**。

   ![[Windows の設定] メニュー](../../media/ag06-diagnostic.png)

3. [プライバシー] で、フィードバック **に対して [診断&を選択し、** オプションの **診断データを選択します**。

   ![[診断とフィードバック] メニュー](../../media/ag07a-diagnostic.png)

Windows 診断設定の構成の詳細については、「組織内での Windows 診断データの [構成」を参照してください](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)。

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>アプリケーションの Application Guard が有効Office機能を確認する

Application Guard for Office が有効になっているか確認する前に、ポリシーが展開されているデバイスで Word、Excel、または PowerPoint を起動します。 アクティブ化Office確認します。 作業 ID を使用して、最初に製品のライセンス認証Office必要な場合があります。

Application Guard for Office有効になっているか確認するには、Word、Excel、または PowerPoint を起動し、信頼されていないドキュメントを開きます。 たとえば、インターネットからダウンロードされたドキュメントや、組織外のユーザーからのメールの添付ファイルを開く場合があります。

信頼されていないファイルを初めて開いた場合、次のOfficeスプラッシュ画面が表示される場合があります。 Application Guard for Officeがアクティブ化され、ファイルが開いている間は、しばらくの間表示される場合があります。 信頼されていないファイルをそれ以降に開く方が速くなります。

![Officeスプラッシュ画面](../../media/ag08-confirm.png)

ファイルを開いた後、ファイルが Application Guard 内でファイルを開いたという視覚的なインジケーターが表示Office。

* リボンの吹き出し

  ![小さな App Guard のメモを示すドキュメント ファイル](../../media/ag09-confirm.png)

* タスク バーに盾が表示されたアプリケーション アイコン

  ![タスク バーのアイコン](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>アプリケーション用に Application Guard をOffice

Office次のポリシーをサポートし、アプリケーションの Application Guard の機能を構成Office。 これらのポリシーは、グループ ポリシーまたはクラウド ポリシー サービスOffice構成できます。

> [!NOTE]
> これらのポリシーを構成すると、Application Guard で開いたファイルの一部の機能が無効Office。

|ポリシー|説明|
|---|---|
|アプリケーションに Application Guard を使用Office|このポリシーを有効にすると、Word、Excel、および PowerPoint は、Application Guard for Office の代わりに保護ビュー分離コンテナーを使用Office。 このポリシーを使用すると、Microsoft Edge に対して Application Guard を有効Office問題がある場合に、アプリケーションの Application Guard を一時的に無効にできます。|
|コンテナーの事前作成Office Application Guard を構成する|このポリシーは、信頼されていないファイルを分離する Office コンテナー用の Application Guard が、実行時のパフォーマンスを向上するために事前に作成されたかどうかを決定します。 この設定を有効にした場合、コンテナーの事前作成を続行する日数を指定するか、Office 組み込みのヒューリスティックでコンテナーを事前に作成できます。
|Application Guard で開いたドキュメントのコピー/貼りOfficeを許可Office|このポリシーを有効にすると、ユーザーは Application Guard for Office で開いたドキュメントから、その外部で開いたドキュメントにコンテンツをコピーして貼り付けできません。|
|Application Guard でハードウェア アクセラレータを無効にしてOffice|このポリシーは、Application Guard for Officeグラフィックスのレンダリングにハードウェア アクセラレータを使用するかどうかを制御します。 この設定を有効にした場合、Office 用 Application Guard はソフトウェア ベース (CPU) レンダリングを使用し、サード パーティ製のグラフィックス ドライバーを読み込み、接続されているグラフィックス ハードウェアを操作しません。
|Application Guard でサポートされていないファイルの種類の保護を無効Office|このポリシーは、Application Guard for Office がサポートされていないファイルの種類を開くのをブロックするか、または保護されたビューへのリダイレクトを有効にするかどうかを制御します。
|Application Guard で開いたドキュメントのカメラとマイクへのアクセスをオフOffice|このポリシーを有効にすると、Officeの Application Guard 内のカメラとマイクへのアクセスがOffice。|
|Application Guard で開いているドキュメントからの印刷を制限Office|このポリシーを有効にすると、Application Guard で開いたファイルからユーザーが印刷できるプリンターがOffice。 たとえば、このポリシーを使用して、ユーザーが PDF にのみ印刷できるよう制限できます。|
|ユーザーが Application Guard を削除してファイルを保護Office防ぐ|このポリシーを有効にすると、(Office アプリケーション エクスペリエンス内で) Office 保護の Application Guard を無効にしたり、Application Guard for Office の外部でファイルを開くオプションが削除されます。 <p> **注:** このポリシーは、ファイルから手動で削除するか、ドキュメントを信頼できる場所に移動することでバイパスできます。|
|

> [!NOTE]
> 次のポリシーを有効にするには、ユーザーがサインアウトして Windows に再びサインインする必要があります。
>
> * Application Guard で開いたドキュメントのコピー/貼り付けを無効Office
> * Application Guard で開いているドキュメントの印刷を制限Office
> * Application Guard で開いたドキュメントへのカメラとマイクのアクセスをオフOffice

## <a name="submit-feedback"></a>フィードバックの送信

### <a name="submit-feedback-via-feedback-hub"></a>フィードバック Hub 経由でフィードバックを送信する

Application Guard for Office を起動するときに問題が発生した場合は、フィードバック Hub からフィードバックを送信してください。

1. フィードバック Hub **アプリを開き** 、サインインします。

2. Application Guard の起動中にエラー ダイアログが表示された場合は、エラー ダイアログで **[Microsoft** に報告] を選択して、新しいフィードバックの送信を開始します。 それ以外の場合は、Application Guard の適切なカテゴリを選択するために移動し、右側にある [新しいフィードバックの追加 <https://aka.ms/mdagoffice-fb> ] を **+ &nbsp;** 選択します。

3. [フィードバックの要約]ボックスに概要を入力します (まだ入力されていない場合)。

4. 発生した問題の詳細な説明と実行した手順を [詳細] ボックスに入力し、[次へ] を選択 **します**。

5. [問題] の横にあるバブルを **選択します**。 選択したカテゴリがセキュリティとプライバシーに関する Microsoft Defender Application Guard Officeし、[ **\> 次へ**] を選択 **します**。

6. [新 **しいフィードバック] を選択し**、[次へ] **を選択します**。

7. 問題に関するトレースを収集します。

   1. [問題 **の再作成] タイルを展開** します。

   2. Application Guard の実行中に問題が発生した場合は、Application Guard インスタンスを開きます。 インスタンスを開く場合、Application Guard コンテナー内から追加のトレースを収集できます。

   3. [Start **recording] (** レコーディングの開始) を選び、タイルの回転が止まるのを待ち、[記録の停止] と *言います*。

   4. Application Guard の問題を完全に再現します。 再現には、Application Guard インスタンスを起動しようとして失敗するまで待機したり、実行中の Application Guard インスタンスで問題を再現したりすることがあります。

   5. [記録の **停止] タイルを選択** します。

   6. 実行中の Application Guard インスタンスは、申請後数分間でも開いた状態にしておき、コンテナー診断も収集できます。

8. 問題に関連するスクリーンショットやファイルを添付します。

9. **[送信]** を選択します。

### <a name="submit-feedback-via-office-customer-voice"></a>カスタマー ボイスを使用してOfficeを送信する

また、Application Guard でドキュメントを開Office問題が発生した場合は、Officeからフィードバックを送信できます。 フィードバックの提出 [についてはOffice Insider ハンド](https://insider.office.com/handbook) ブックを参照してください。

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Microsoft Defender for Endpoint および Microsoft Defender for Office 365 との統合

Application Guard for Office Microsoft Defender for Endpoint と統合され、分離された環境で発生する悪意のあるアクティビティの監視と警告を提供します。

Microsoft Defender for Endpoint は、エンタープライズ ネットワークが高度な脅威を防止、検出、調査、および対応するために設計されたセキュリティ プラットフォームです。 このプラットフォームについて詳しくは [、「Microsoft Defender for Endpoint」をご覧ください](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp)。 このプラットフォームへのデバイスのオンボードについて詳しくは、「エンドポイント向け Microsoft Defender サービスへのデバイスのオンボード」 [をご覧ください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)。

また、Office 365 用に Microsoft Defender をエンドポイント用の Defender と組み合Office構成できます。 詳しくは、「Microsoft Defender for Endpoint と [Office 365](integrate-office-365-ti-with-wdatp.md)の Defender の統合」をご覧ください。

## <a name="limitations-and-considerations"></a>制限事項と考慮事項

* Office 用 Application Guard は、信頼できる企業リソース、イントラネット、ユーザーの ID、およびコンピューター上の任意のファイルにアクセスできない、信頼されていないドキュメントを分離する制限付きモードです。 その結果、ユーザーがこのようなアクセスに依存する機能 (ディスク上のローカル ファイルから画像を挿入するなど) にアクセスしようとすると、アクセスが失敗し、次の例のようなプロンプトが表示されます。 信頼されていないドキュメントが信頼できるリソースにアクセスするには、ユーザーがドキュメントから Application Guard 保護を削除する必要があります。

  ![[安全に保つために、この機能は使用できません] というダイアログ ボックス](../../media/ag10-limitations.png)

  > [!NOTE]
  > ファイルとそのソース、またはファイルの送信元を信頼している場合にのみ、保護を削除する必要があります。

* Application Guard では、マクロやコントロールActiveXドキュメント内のアクティブなコンテンツが無効Office。 アクティブなコンテンツを有効にするには、Application Guard 保護を削除する必要があります。

* ネットワーク共有からの信頼できないファイル、または別の組織の OneDrive、OneDrive for Business、または SharePoint Online から共有されたファイルは、Application Guard で読み取り専用として開きます。 ユーザーは、そのようなファイルのローカル コピーを保存してコンテナー内で作業を続行したり、保護を削除して元のファイルを直接操作することができます。

* Information Rights Management (IRM) によって保護されているファイルは、既定でブロックされます。 ユーザーがこのようなファイルを保護ビューで開く場合、管理者は、組織でサポートされていないファイルの種類のポリシー設定を構成する必要があります。

* Office 用 Application Guard で Office アプリケーションに対するカスタマイズは、ユーザーがサインアウトして再びサインインした後、またはデバイスの再起動後に保持されません。

* UIA フレームワークを使うアクセシビリティ ツールだけが、アプリ用 Application Guard で開いたファイルにアクセシビリティ対応のエクスペリエンスOffice。

* インストール後に Application Guard を初めて起動するには、ネットワーク接続が必要です。 Application Guard がライセンスを検証するには、接続が必要です。

* ドキュメントの情報セクションでは、 *最終* 変更者プロパティに **ユーザーとして WDAGUtilityAccount** が表示される場合があります。 WDAGUtilityAccount は、Application Guard で構成された匿名ユーザーです。 デスクトップ ユーザーの ID は、Application Guard コンテナー内では共有されます。

## <a name="performance-optimizations-for-application-guard-for-office"></a>Application Guard for Office のパフォーマンスの最適化

このセクションでは、Application Guard で使用されるパフォーマンスの最適化の概要をOffice。 この情報は、Application Guard が有効な場合に、管理者が Office またはシステム全体のパフォーマンスに関連するユーザーからのレポートを診断するのに役立ちます。

Application Guard は、仮想化されたコンテナーを使用して、信頼されていないドキュメントをシステムから分離します。 コンテナーを作成し、application Guard コンテナーを設定して Office ドキュメントを開くプロセスでは、パフォーマンスのオーバーヘッドが発生し、ユーザーが信頼されていないドキュメントを開く際のユーザー エクスペリエンスに悪影響を及ぼす可能性があります。

ユーザーに期待されるファイルを開くエクスペリエンスを提供するために、Application Guard はロジックを使用して、システムで次のヒューリスティックが満たされた場合にコンテナーを事前に作成します。ユーザーが過去 28 日間に保護ビューまたは Application Guard でファイルを開いている。

このヒューリスティックが満たOffice、ユーザーが Windows にサインインした後、ユーザーの Application Guard コンテナーが事前に作成されます。 この作成前操作の進行中は、システムのパフォーマンスが低下する可能性がありますが、操作が完了するとすぐに効果が解決されます。

> [!NOTE]
> ヒューリスティックがコンテナーを事前に作成するために必要なヒントは、ユーザーがコンテナーを使用Officeアプリケーションによって生成されます。 Application Guard が有効になっている新しいシステムに Office をインストールした場合、Office は、ユーザーがシステム上で信頼されていないドキュメントを初めて開くまでコンテナーを事前に作成しません。 ユーザーは、この最初のファイルが Application Guard で開くのに時間がかかるのを確認します。

## <a name="known-issues"></a>既知の問題

* Web リンク (または) を `http` 選択 `https` しても、ブラウザーは開かれません。
* Application Guard で開いたドキュメントにリッチ テキスト形式 (RTF) Office画像を貼り付けはまだサポートされていません。
* .NET の更新により、Application Guard でファイルが開けなきます。 回避策として、ユーザーは、このエラーが発生した場合にデバイスを再起動できます。 Application Guard または Windows サンドボックスを開こうとすると、エラー メッセージを受信するWindows Defender [詳細を確認してください](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)。
