---
title: エンドポイント DLP の使用
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: エンドポイント データ損失防止の場所を使用するためのデータ損失防止 (DLP) ポリシーを構成する方法を説明します。
ms.openlocfilehash: 9107759e137d7b8dd86253f9c6567b76686d2518
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66632379"
---
# <a name="using-endpoint-data-loss-prevention"></a>エンドポイント データ損失防止の使用

エンドポイント DLP 機能、および DLP ポリシーで表示される方法を把握するために、いくつかのシナリオをまとめてましたので、確認してください。

> [!IMPORTANT]
> これらのエンドポイント DLP シナリオは、DLP ポリシーの作成と調整に関する公式な手順ではありません。 一般的な状況で DLP ポリシーを使用する必要がある場合は、次のトピックを参照してください。
>
>- [Microsoft Purview データ損失防止についての説明](dlp-learn-about-dlp.md)
>- [DLP の既定ポリシーの概要](get-started-with-the-default-dlp-policy.md)
>- [テンプレートから DLP ポリシーを作成する](create-a-dlp-policy-from-a-template.md)
>- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)

## <a name="scenario-1-create-a-policy-from-a-template-audit-only"></a>シナリオ 1: テンプレートからポリシーを作成 (監査のみ)

これらのシナリオでは、デバイスが既にオンで、アクティビティエクスプローラーに報告されている必要があります。 まだデバイスをオンにしていない場合は、[エンドポイントのデータ損失防止 (プレビュー) を開始](endpoint-dlp-getting-started.md)を参照してください。

1. [データ損失防止ポリシー ページ](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開きます。

2. **[ポリシーの作成]** を選びます。

3. このシナリオでは、**[プライバシー]** を選択して、"**米国の個人情報 (PII) データ**" を選んでから、**[次へ]** を選びます。

4. **[デバイス]** を除くすべての場所で **[状態]** フィールドをオフにします。**[次へ]** を選択します。

5. 規定の **確認してテンプレートから設定をカスタマイズ** の選択を承認して、**次へ** を選択します。

6. 既定の **保護アクション** の値を承認して、**次へ** を選択します。

7. **[Windows デバイスでアクティビティを監査または制限する]** を選択して、**[監査のみ]** に設定されたアクションはそのままにしておきます。**[次へ]** を選択します。

8. 既定の **[先にテストを行います]** を承認し、**[テスト モードでポリシーのヒントを表示]** を選択します。**[次へ]** を選択します。

9. 設定を確認し、**送信** を選択します。

10. 新しい DLP ポリシーがポリシー一覧に表示されます。

11. 監視対象エンドポイントのデータについてアクティビティ エクスプローラーを確認します。デバイスの [場所] フィルターを設定してポリシーを追加してから、ポリシー名でフィルター処理して、このポリシーの影響を確認します。必要な場合は、「[アクティビティ エクスプローラーを使用して作業を開始する](data-classification-activity-explorer.md)」を参照してください。

12. 米国の個人情報 (PII) データの条件をトリガーするコンテンツを含むテストを組織外のユーザーと共有してみます。この試行により、ポリシーがトリガーされます。

13. イベントのアクティビティエクスプローラーを確認します。

## <a name="scenario-2-modify-the-existing-policy-set-an-alert"></a>シナリオ 2: 既存のポリシーを変更し、通知を設定

1. [データ損失防止ポリシー](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開く。

2. シナリオ １ で作成した **米国の個人情報 (PII) データ** ポリシーを選択します。

3. **[ポリシーの編集]** を選びます。

4. **詳細な DLP ルール** ページに移動し、**米国の個人を特定できる情報が検出された低ボリュームのコンテンツ** を編集します。

5. **インシデントリポート** セクションまでスクロールして、**ルールが一致する場合、管理者に通知を送信** を **オン** に設定します。 メールの通知は、管理者と、受信者のリストに追加する他のユーザーに自動的に送信されます。 

![turn-on-incident-reports。](../media/endpoint-dlp-2-using-dlp-incident-reports.png)
   
6. このシナリオの目的で、**アクティビティーがこのルールに一致する度に通知を送信** を選択します。

7. **[保存]** を選択します。

8. **次へ** を選択して、ポリシーの変更を **送信** を選択することで、すべての前の設定を保持します。

9. 米国の個人情報 (PII) データの条件をトリガーするコンテンツを含むテストを組織外のユーザーと共有してみます。この試行により、ポリシーがトリガーされます。

10. イベントのアクティビティエクスプローラーを確認します。

## <a name="scenario-3-modify-the-existing-policy-block-the-action-with-allow-override"></a>シナリオ 3: 既存のポリシーを変更し、上書きを許可する操作をブロック

1. [データ損失防止ポリシー](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開く。

2. シナリオ １ で作成した **米国の個人情報 (PII) データ** ポリシーを選択します。

3. **[ポリシーの編集]** を選びます。

4. **詳細な DLP ルール** ページに移動し、**米国の個人を特定できる情報が検出された低ボリュームのコンテンツ** を編集します。

5. **Windows デバイスでアクティビティを監査または制限** セクションまでスクロールして、アクティビティごと対応するアクションに **上書きをブロック** を設定します。

   > [!div class="mx-imgBorder"]
   > ![上書きアクションのブロックを設定。](../media/endpoint-dlp-6-using-dlp-set-blocked-with-override.png)
   
6. **[保存]** を選択します。

7. **米国の個人情報が検出された大量のコンテンツ** の手順4から手順７を繰り返します。

8. **次へ** を選択して、ポリシーの変更を **送信** を選択することで、すべての前の設定を保持します。

9. 米国の個人情報 (PII) データの条件をトリガーするコンテンツを含むテストを組織外のユーザーと共有してみます。この試行により、ポリシーがトリガーされます。

   クライアントデバイスに次のようなポップアップが表示されます。

   > [!div class="mx-imgBorder"]
   > ![エンドポイント DLP クライアントが上書き通知をブロックしました。](../media/endpoint-dlp-3-using-dlp-client-blocked-override-notification.png)

10. イベントのアクティビティエクスプローラーを確認します。

## <a name="scenario-4-avoid-looping-dlp-notifications-from-cloud-synchronization-apps-with-auto-quarantine-preview"></a>シナリオ 4: 自動検疫を使用して、クラウド同期アプリからの DLP 通知のループを回避する (プレビュー)

### <a name="before-you-begin"></a>始める前に

このシナリオでは、**非常に機密性の高い社外秘** の秘密度ラベルを持つファイルの OneDrive への同期がブロックされます。 これは、複数のコンポーネントと手順からなる複雑なシナリオです。 以下が必要です。

- 対象となる AAD ユーザー アカウントと、ローカルの OneDrive フォルダーと OneDrive クラウド ストレージをすでに同期させているオンボード済みの Windows 10 コンピューター。
- 対象の Windows 10 コンピューターにインストールされた Microsoft Word
- 秘密度ラベルが構成され、発行されました。「[秘密度ラベルの使用を開始する](get-started-with-sensitivity-labels.md#get-started-with-sensitivity-labels)」および「[秘密度ラベルとそのポリシーを作成して構成する](create-sensitivity-labels.md#create-and-configure-sensitivity-labels-and-their-policies)」を参照してください。

3 つの手順があります。

1. エンドポイント DLP の自動検疫設定を構成します。
2. **非常に機密性の高い社外秘** の秘密度ラベルが付けられた機密性の高いアイテムをブロックするポリシーを作成します。
3. ポリシーの対象となる Windows 10 デバイスで Word ドキュメントを作成し、ラベルを適用して、同期されるユーザー アカウントのローカル OneDrive フォルダーにコピーします。  

### <a name="configure-endpoint-dlp-unallowed-app-and-auto-quarantine-settings"></a>エンドポイント DLP の許可されていないアプリと自動検疫設定を構成する

1. [[エンドポイント DLP 設定]](https://compliance.microsoft.com/datalossprevention?viewid=globalsettings) を開きます

2. **[許可されていないアプリ]** を展開します。

3. **[許可されていないアプリの追加または編集]** を選択し、表示名に *[OneDrive]*、実行名に *[onedrive.exe]*  を追加して、onedrive.exe による「**非常に機密性の高い社外秘**」ラベルのアイテムへのアクセスを禁止します。

4. **[自動検疫]** を選んでから **[保存]** を選びます。

5. **[自動検疫設定]** で **[自動検疫設定の編集]** を選びます。

6. **[許可されていないアプリへの自動検疫]** を有効にします。

7. オリジナルの機密ファイルを移動させるローカル マシン上のフォルダーへのパスを入力します。次に例を示します。
   
    ユーザー名 *Isaiah langer* 向けの **'%homedrive%%homepath%\Microsoft DLP\Quarantine'** は、移動済みアイテムを次の名前のフォルダーに配置します。  

    *C:\Users\IsaiahLanger\Microsoft DLP\Quarantine\OneDrive*

    元のファイル名に日付とタイム スタンプを追加します。
    
    > [!NOTE]
    > DLP 自動検疫では、許可されていないアプリごとにファイルのサブフォルダーが作成されます。 つまり、許可されていないアプリの一覧に *Notepad* と *OneDrive* の両方が入っている場合、**\OneDrive** 用のサブフォルダーと **\Notepad** 用のサブフォルダーが作成されます。

8. **[次のテキストを含む .txt ファイルでファイルを置き換える]** を選択し、プレースホルダー ファイルに必要なテキストを入力します。たとえば、*auto quar 1.docx* という名前のファイルの場合:
    
    > %%FileName%% には、組織がデータ損失防止 (DLP) ポリシーで保護している %%PolicyName%% が含まれ、検疫フォルダー %%QuarantinePath%% に移動されました。
    
    は、以下のメッセージを含むテキスト ファイルを残します。
    
    > auto quar 1.docx には、組織でデータ損失防止 (DLP) ポリシーで保護されている機密情報が含まれており、検疫フォルダー「C:\Users\IsaiahLanger\Microsoft DLP\Quarantine\OneDrive\auto quar 1_20210728_151541.docx」に移動されました。

9. **[保存]** を選択します。

### <a name="configure-a-policy-to-block-onedrive-synchronization-of-files-with-the-sensitivity-label-highly-confidential"></a>秘密度ラベルが「非常に機密性の高い社外秘」であるファイルの OneDrive 同期をブロックするポリシーを構成します。

1. [データ損失防止ポリシー ページ](https://compliance.microsoft.com/datalossprevention?viewid=policies)を開きます。

2. **[ポリシーの作成]** を選びます。

3. このシナリオでは、**[カスタム]** を選択し、**[カスタム ポリシー]** を選択して、**[次へ]** を選択します。

4. **[名前]** フィールドおよび **[説明]** フィールドに入力し、**[次へ]** を選択します。

5. **状態** フィールドを **デバイス** を除くすべての場所でオフにします。 テストする特定のエンド ユーザー アカウントがある場合は、必ず範囲内で選択してください。 **次へ** を選択します。

6. 既定の **[高度な DLP ルールの作成またはカスタマイズ]** の選択を承諾し、**[次へ]** を選択します。

7. 以下の値でルールを作成します。
    1. **[名前]** > *[シナリオ 4 自動検疫]*。
    1. **[条件]** > **[コンテンツに含まれている]** > **[秘密度ラベル]** > **[非常に機密性の高い社外秘]**。
    1.  **[アクション]** > **[Windows デバイス上のアクティビティの監査または制限]** > **[許可されていないアプリでアクセス]** > **[ブロック]**。 このシナリオでは、他のアクティビティをすべてクリアします。
    1. **[ユーザー通知]** > **[オン]**。
    1. **[エンドポイント デバイス]** から、**[アクティビティの場合にユーザーにポリシー ヒント通知を表示する]** がまだ有効になっていない場合は選択します。
    
8. **[保存]**、**[次へ]** を選択します。

9. **[すぐにオンにする]** を選択します。**[次へ]** を選択します。

10. 設定を確認し、**送信** を選択します。

    > [!NOTE]
    > 新しいポリシーが複製され、対象の Windows 10 コンピューターに適用されるまで 1 時間以上かかります。

11. 新しい DLP ポリシーがポリシー一覧に表示されます。

### <a name="test-auto-quarantine-on-the-windows-10-device"></a>Windows 10 デバイスでの自動検疫のテスト

1. 「[秘密度ラベルが「非常に機密性の高い社外秘」であるファイルの OneDrive 同期をブロックするポリシーを構成します](#configure-a-policy-to-block-onedrive-synchronization-of-files-with-the-sensitivity-label-highly-confidential)」の手順 5 で指定したユーザー アカウントを使用して Windows 10 コンピューターにログインします。

2. 内容が OneDrive に同期されないフォルダーを作成します。次に例を示します。

    *C:\auto-quarantine ソース フォルダー*

3. Microsoft Word を開き、自動検疫ソース フォルダーにファイルを作成します。 **機密性の高い社外秘** の秘密度ラベルを貼付します。「[Office のファイルとメールに秘密度ラベルを適用する](https://support.microsoft.com/topic/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)」を参照してください。

4. 作成したばかりのファイルを、OneDrive 同期フォルダーにコピーします。 アクションが許可されておらず、ファイルが検疫される予定であることを伝えるユーザー通知トーストが表示されます。 たとえば、ユーザー名「*Isaiah Langer*」、タイトル「*auto-quarantine doc 1.docx*」のドキュメントの場合、次のようなメッセージが表示されます。

    ![指定されたファイルに OneDrive 同期アクションが許可されておらず、ファイルが検疫されることを示すデータ損失防止ユーザー通知ポップアップ。](../media/auto-quarantine-user-notification-toast.png)
    
    メッセージは以下のとおりです。
    
    > autoquarantine doc 1.docx をこのアプリで開くことは許可されていません。 このファイルは 'C:\Users\IsaiahLanger\Microsoft DLP\OneDrive' に検疫されます

5. **[無視]** を選択します。

6. プレース ホルダー テキスト ファイルを開きます。 **auto-quarantine doc 1.docx_ *date_time*.txt** という名前が付けられます。 

7. 検疫フォルダーを開き、元のファイルがそこにあることを確認します。
 
8. 監視対象エンドポイントのデータについてアクティビティ エクスプローラーを確認します。デバイスの [場所] フィルターを設定してポリシーを追加してから、ポリシー名でフィルター処理して、このポリシーの影響を確認します。必要な場合は、「[アクティビティ エクスプローラーを使用して作業を開始する](data-classification-activity-explorer.md)」を参照してください。

9. イベントのアクティビティエクスプローラーを確認します。

## <a name="scenario-5-restrict-unintentional-sharing-to-unallowed-cloud-apps-and-services"></a>シナリオ 5: 意図しない共有を許可されていないクラウド アプリとサービスに制限する

Endpoint DLP と Edge Web ブラウザを使用すると、許可されていないクラウドアプリとサービスで意図しない機密アイテムの共有を制限できます。 Microsoft Edge では、アイテムがエンドポイント DLP ポリシーによって制限される場合を把握して、アクセス制限を適用しています。

適切に設定された DLP ポリシーで **［デバイス］** を場所として選択し、Microsoft Edge ブラウザを使用すると、これらの設定で定義した許可されていないブラウザは、DLP ポリシーの制御に一致する機密アイテムにアクセスすることができなくなります。 代わりに、ユーザーは Microsoft Edge を使用するためにリダイレクトされます。DLP に課される制限を理解すると、DLP ポリシーの条件が満たされた場合にアクティビティをブロックまたは制限できます。

この制限を使用するには、次の 3 つの重要な要素を構成する必要があります。

1. 機密アイテムの共有を禁止する場所 (サービス、ドメイン、IP アドレス) を指定します。

2. DLP ポリシーが一致した場合に、特定の機密アイテムへのアクセスを許可しないブラウザーを追加します。

3. **クラウドサービスへアップロード** と **許可していないブラウザーからのアクセス** の設定をオンにし、DLP ポリシーを構成してから、これらの場所でアップロードを制限する機密アイテムの種類を定義します。

新しいサービス、アプリ、およびポリシーを継続的に追加して、制限を拡張、強化しながら、ビジネスへのニーズを満たし機密データを保護できます。 

この構成により、データが安全に維持でき、ユーザーが機密情報以外のアイテムにアクセスしたり、共有したりすることを禁止または制限する不必要な制約も回避できます。
## <a name="see-also"></a>関連項目

- [エンドポイント データ損失防止について](endpoint-dlp-learn-about.md)
- [エンドポイント データ損失防止を開始する](endpoint-dlp-getting-started.md)
- [データ損失防止について](dlp-learn-about-dlp.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [Activity Explorer を使い始める](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/)
- [Windows 10 デバイスと Windows 11 デバイスを Microsoft Purview にオンボードする](/microsoft-365/compliance/device-onboarding-overview)
- [Microsoft 365 サブスクリプション](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure Active Directory (AAD) が参加しました](/azure/active-directory/devices/concept-azure-ad-join)
- [Chromium ベースの新しい Microsoft Edge をダウンロードする](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
- [DLP の既定ポリシーの概要](get-started-with-the-default-dlp-policy.md)
- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md)
