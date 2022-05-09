---
title: ビジネス向けのMicrosoft 365をセキュリティで保護するためのベスト プラクティス
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
- admindeeplinkDEFENDER
- adminvideo
- admindeeplinkEXCHANGE
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: de2da300-dbb6-4725-bb12-b85a9d296e75
description: ランサムウェア、フィッシング、悪意のある添付ファイルなど、サイバー脅威からビジネス メールとデータを保護します。
ms.openlocfilehash: 18de5e6f0d859095f38972b0fae66c1312bf4099
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093669"
---
# <a name="best-practices-for-securing-microsoft-365-for-business"></a>ビジネス向けのMicrosoft 365をセキュリティで保護するためのベスト プラクティス

Microsoft のビジネス プランのいずれかを使用している小規模または中規模の組織の場合、この記事のガイダンスは、組織のセキュリティを強化するのに役立ちます。 選択肢の中でも、Microsoft Defender for Businessやその他の[セキュリティ保護](../../business-premium/get-microsoft-365-business-premium.md)が含まれるようになったため、Microsoft 365 Business Premiumが先導します。 ここに含まれる推奨されるアクションは、「強い思い出を持つ人が自分の目標を達成するのに役立 [ちます。これは](https://go.microsoft.com/fwlink/p/?linkid=2015598)、この目標を達成するのに役立ちます。これは、この目標を達成するのに役立ちます。

> [!TIP]
> この記事の手順に関するヘルプが必要な場合は、 [Microsoft の小規模ビジネス スペシャリストと連携](https://go.microsoft.com/fwlink/?linkid=2186871)することを検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。

## <a name="watch-a-quick-overview-of-security"></a>ウォッチ: セキュリティの概要

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mzxI?autoplay=false]

すべてのMicrosoft 365プランでは、Defender ウイルス対策によるベースライン保護とセキュリティが提供されますが、Microsoft 365 Business Premiumでは、Microsoft Defender for Businessが含まれているため、脅威保護、データ保護、デバイス管理機能も備えています。  これらの追加機能により、組織をオンラインの脅威や不正アクセスから保護し、携帯電話、タブレット、コンピューターで会社のデータを管理できます。

## <a name="security-features-comparison"></a>セキュリティ機能の比較

サービス プランの機能の 1 つについて確認するには、次の表の見出しをクリックします。 

|タスク|Microsoft 365 Business Standard|Microsoft 365 Business Premium|
|---|---|---|
[パスワードの紛失または盗難から保護する](#set-up-multifactor-authentication) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
[ユーザーをトレーニングする](#train-your-users) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
[専用の管理者アカウントを使用する](#use-dedicated-admin-accounts)|![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | 
[マルウェアから保護する](#protect-against-malware) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(電子メールの保護) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(電子メールとデバイスの保護の強化) |
[ランサムウェアから保護する](#protect-against-ransomware) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(電子メールとクラウド ストレージの保護) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(デバイス、電子メール、クラウド ストレージの保護の強化) |
[機密性の高いメールを暗号化する](#send-encrypted-email) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
[フィッシング攻撃からメールを保護する](#protect-sensitive-emails) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(フィッシング対策保護) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(高度なフィッシング対策保護) |
[メール ファイルとOffice ファイル内の悪意のある添付ファイル、ファイル、URL から保護する](#protect-against-malicious-attachments-files-and-urls) | | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(セーフ リンクと添付ファイルセーフ) |
[組織のデバイスの保護を強化する](#increase-protection-for-your-organizations-devices) | | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(エンタープライズ グレードのデバイス保護) |

セキュリティをすばやく設定し、[Microsoft 365 Business Premium](../../business-premium/index.md) ライブラリで提供されているガイダンスを使用して安全に共同作業を開始できます。 ビジネス プレミアム情報は、高度なサイバー攻撃やハッカーによって起動されたサイバー脅威からすべての中小企業のお客様を保護するために、Microsoft 防御のデモクラシー チームと協力して開発されました。

### <a name="about-the-microsoft-365-secure-score"></a>Microsoft 365セキュリティスコアについて

開始する前に、Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">ポータル</a>で[Microsoft 365セキュリティ](../../security/defender/microsoft-secure-score.md)スコアを確認することが重要です。 一元化されたダッシュボードから、Microsoft 365 ID、データ、アプリ、デバイス、インフラストラクチャのセキュリティを監視および向上させることができます。 推奨されるセキュリティ機能の構成、セキュリティ関連のタスクの実行 (レポートの表示など)、サード パーティ製のアプリケーションまたはソフトウェアを使用した推奨事項への対処に関するポイントが与えられます。 より広範な Microsoft 製品とサービスのセットに対する分析情報と可視性を高め、組織のセキュリティ正常性に関する自信を持って報告できます。

![Microsoft セキュリティ スコアのスクリーンショット。](../../media/secure-score.png)

## <a name="set-up-multifactor-authentication"></a>多要素認証を設定する

多要素認証 (MFA) を使用して、パスワードの紛失や盗難から保護します。 多要素認証が設定されている場合、ユーザーは携帯電話のコードを使用してMicrosoft 365にサインインする必要があります。 この追加の手順では、ハッカーがパスワードを知っている場合に引き継ぐのを防ぐことができます。 

多要素認証は、2 段階認証とも呼ばれます。 個人は、Google や Microsoft アカウントなど、ほとんどのアカウントに 2 段階認証を簡単に追加できます。 [個人用 Microsoft アカウントに 2 段階認証を追加する方法を次に示します](https://go.microsoft.com/fwlink/p/?linkid=2016403)。

Microsoft 365を使用している企業の場合は、ユーザーが多要素認証を使用してログインする必要がある設定を追加します。 この変更を行うと、ユーザーは次回ログインするときに、2 要素認証用に電話を設定するように求められます。
MFA を設定する方法とユーザーがセットアップを完了する方法に関するトレーニング ビデオについては、「MFA と[ユーザーのセットアップ](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)の[設定](set-up-multi-factor-authentication.md)」を参照してください。

### <a name="turn-on-security-defaults"></a>セキュリティの既定値を有効にする

ほとんどの組織では、セキュリティの既定値により、適切なレベルのサインイン セキュリティが追加されます。 詳細については、「[セキュリティの既定値とは](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」を参照してください。 サブスクリプションが新しい場合は、セキュリティの既定値が自動的に有効になっている可能性があります。

Azure portalのAzure Active Directory (Azure AD) の **[プロパティ**] ウィンドウで、セキュリティの既定値を有効または無効にします。

1. グローバル管理者の資格情報を使用して、[MIcrosoft 365 管理センター](https://admin.microsoft.com) にサインインします。

2. 左側のナビゲーションで、**[すべて表示]** を選択し、**[管理センター]** の **[Azure Active Directory]** を選択します。

3. **Azure Active Directory管理センター** で、**Azure Active Directory** >  **Properties** を選択します。

4. ページの下部で、**[セキュリティの既定値の管理]** を選択します。

5. セキュリティの規定値を有効にするには **[はい]** を選び、セキュリティの規定値を無効にするには **[いいえ]** を選んで、**[保存]** を選択します。

組織に多要素認証を設定した後、ユーザーはデバイスに 2 段階認証を設定する必要があります。 詳細については、「[Microsoft 365の 2 段階認証を設定する」を](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)参照してください。

> [!Tip]
> 多要素認証をより細かく制御する必要がある場合は、Microsoft 365 Business Premiumを使用して条件付きアクセスを有効にすることができます。 これを行う場合は、同等のポリシーを Security Defaults に実装することをお勧めします。 [セキュリティの既定値](/microsoft-365/business-premium/m365bp-conditional-access)の詳細については、こちらを参照してください。

詳細と推奨事項については、「 [ユーザーの多要素認証を設定する」を](set-up-multi-factor-authentication.md)参照してください。

## <a name="train-your-users"></a>ユーザーをトレーニングする

「中立大学ケネディ学校 [サイバーセキュリティ キャンペーン の手引き」](https://go.microsoft.com/fwlink/p/?linkid=2015598) では、フィッシング攻撃を特定するためのユーザーのトレーニングなど、組織内のセキュリティ意識の強い文化を確立するための優れたガイダンスを提供します。

さらに、Microsoft では、ユーザーが「 [ハッカーやマルウェアからアカウントとデバイスを保護](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6)する」に記載されているアクションを実行することをお勧めします。 それらの操作を次に示します。

- 強力なパスワードを使用する
- デバイスの保護
- Windows 10 PC と Mac PC でセキュリティ機能を有効にする

また、Microsoft では、次の記事で推奨されるアクションを実行して、ユーザーが個人用メール アカウントを保護することをお勧めします。

- [Outlook.com メール アカウントを保護する](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [2 段階認証で Gmail アカウントを保護する](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="use-dedicated-admin-accounts"></a>専用の管理者アカウントを使用する

Microsoft 365環境の管理に使用する管理アカウントには、管理者特権が含まれます。 これらは、ハッカーやサイバー攻撃者にとって有益なターゲットです。 管理者アカウントは、管理にのみ使用します。 管理者は、通常の非管理者用の別のユーザー アカウントを持ち、自分のジョブ機能に関連付けられたタスクを完了するために必要な場合にのみ管理アカウントを使用する必要があります。 追加の推奨事項:

- アカウントが[Azure Active Directory](../../admin/add-users/add-users.md)に追加されていることを確認します。
- 多要素認証用に管理者アカウントも設定されていることを確認します。
- 管理者アカウントを使用する前に、個人用メール アカウントを含め、無関係なすべてのブラウザー セッションとアプリを閉じます。
- 管理者タスクを完了したら、必ずブラウザー セッションからログアウトしてください。

## <a name="protect-against-malware"></a>マルウェアから保護する

Microsoft 365環境には、マルウェアに対する保護が含まれています。 次の方法でマルウェア保護を強化できます。

- [Microsoft Office 365に対して事前設定されたポリシーを使用する](../../../microsoft-365/security/office-365-security/preset-security-policies.md)。
- 特定の種類のファイルを含む添付ファイルをブロックする。
- デバイスでウイルス対策/マルウェア対策の保護を使用する (特にMicrosoft Defender for Business)。 [これには、自動調査レポート](../../security/office-365-security/air-view-investigation-results.md) (AIR) や脅威と脆弱性管理 (TVM) ダッシュボードなどの機能が含まれています。 Microsoft Defender for Businessがプライマリウイルス対策ソフトウェアでない場合でも、パッシブ モードで実行し、[エンドポイントの保護と応答 (EDR)](../../security/defender-endpoint/overview-endpoint-detection-response.md) を使用できます。特に[、ブロック モード](../../security/defender-endpoint/edr-in-block-mode.md)では、EDRの機能によって検出され、プライマリ ウイルス検出ソフトウェアによって見逃された悪意のあるアーティファクトを修復するためにバックグラウンドで動作します。

### <a name="block-attachments-with-certain-file-types"></a>特定の種類のファイルを含む添付ファイルをブロックする

マルウェアの保護を強化するには、マルウェアでよく使用されるファイルの種類を含む添付ファイルをブロックします。 メールでマルウェア保護を強化するには、 [短いトレーニング ビデオ](increase-threat-protection.md#raise-the-level-of-protection-against-malware-in-mail)を表示するか、次の手順を実行します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>で、[**ポリシー**] セクションの [**メールとコラボレーション**] \> [**ポリシーとルール**] \> [**脅威ポリシー**] \> [**マルウェア対策**] に移動します。
2. [ **マルウェア対策** ] ページで、[既定値] をダブルクリック **します**。 ポップアップが表示されます。
3. ポップアップの下部にある [ **保護設定の編集]** を選択します。
4. 次のページの [ **保護の設定**] で、[ **共通の添付ファイル フィルターを有効にする]** の横にあるチェック ボックスをオンにします。 ブロックされているファイルの種類は、このオプションのすぐ下に一覧表示されます。 ファイルの種類を追加または削除するには、リストの末尾にある **[ファイルの種類のカスタマイズ** ] を選択します。
5. **[保存]** を選択します。

詳細については、「 [EOP でのマルウェア対策保護](../../security/office-365-security/anti-malware-protection.md)」を参照してください。

### <a name="use-antivirus-and-anti-malware-protection"></a>ウイルス対策とマルウェア対策の保護を使用する

Microsoft Defender ウイルス対策は強力なウイルス対策とマルウェア対策を提供し、Windows オペレーティング システムに組み込まれています。

組織でMicrosoft 365 Business Premiumを使用している場合は、次を含む追加のデバイス保護が提供されます。

- 次世代の保護
- ファイアウォール保護
- Web コンテンツ フィルタリング

これらの機能は、2022 年 3 月 1 日以降、Microsoft 365 Business Premiumのお客様へのロールアウトを開始するオファリングであるMicrosoft Defender for Businessに含まれています。

[Intune と Microsoft Defender for Endpoint についての詳細情報](../../security/defender-business/mdb-overview.md)。

## <a name="protect-against-ransomware"></a>ランサムウェアから保護する

ランサムウェアは、ファイルを暗号化したり、コンピューター画面をロックしたりすることで、データへのアクセスを制限します。 その後、データへのアクセスと引き換えに、通常はビットコインなどの仮想通貨の形式で"身代金" を求めることによって、被害者からお金を強要しようとします。

Microsoft 365でホストされている電子メールと、OneDriveに格納されているファイルに対してランサムウェア保護を受ける。 Microsoft 365 Business Premiumがある場合は、組織のデバイスに対して追加のランサムウェア保護を受けることができます。

ランサムウェアから保護するには、ランサムウェアでよく使用されるファイル拡張子をブロックする 1 つ以上のメール フロー ルールを作成するか、電子メールでこれらの添付ファイルを受信したユーザーに警告します。 適切な開始点は、次の 2 つのルールを作成することです。

- OneDriveを使用してファイルを移動し、常にアクセス制御と保護を行います。

- マクロを含む添付ファイルOffice開く前に、ユーザーに警告を表示します。 ランサムウェアはマクロ内に隠すことができるので、知らないユーザーからこれらのファイルを開かないようにユーザーに警告します。

- ランサムウェアやその他の悪意のあるコードを含む可能性のあるファイルの種類をブロックします。 まず、実行可能ファイルの一般的な一覧を示します (次の表に示します)。 組織でこれらの実行可能ファイルの種類のいずれかを使用していて、電子メールで送信されることを想定している場合は、前のルールに追加します (ユーザーに警告)。

メール トランスポート ルールを作成するには、 [短いトレーニング ビデオ](increase-threat-protection.md#protect-against-ransomware)を表示するか、次の手順を実行します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。

2. **メール フロー** カテゴリで、**ルール** を選択します。

3. を選択 **+** し、 **新しいルールを作成します**。

4. ダイアログ ボックスの下部にある **** を選択すると、オプションの完全なセットが表示されます。

5. 次の表の各ルールの設定を適用します。 設定を変更する場合を除き、残りの設定は既定のままにしておきます。

6. **[保存]** を選択します。

| Setting | Office ファイルの添付ファイルを開く前にユーザーに警告する | ランサムウェアやその他の悪意のあるコードを含む可能性のあるファイルの種類をブロックする |
|:-----|:-----|:-----|
|名前  <br/> |ランサムウェア対策ルール: ユーザーに警告する  <br/> |ランサムウェア対策ルール: ファイルの種類をブロックする  <br/> |
|次の場合は、この規則を適用します。 . .  <br/> |任意の添付ファイル . . . ファイル拡張子が一致します。 . .  <br/> |任意の添付ファイル . . . ファイル拡張子が一致します。 . .  <br/> |
|単語または語句を指定する  <br/> |次のファイルの種類を追加します。  <br/> dotm, docm, xlsm, sltm, xla, xlam, xll, pptm, potm, ppam, ppsm, sldm  <br/> |次のファイルの種類を追加します。  <br/> ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, vb, vbe, vbs, wsc, wsf, wsh, exe, pif  <br/> |
|次の操作を行います。 . .  <br/> |免責事項の先頭に追加する  <br/> |メッセージをブロックします。 . . メッセージを拒否し、説明を含める  <br/> |
|メッセージ テキストを指定する  <br/> |ファイルに悪意のあるコードが含まれている可能性があり、送信者が安全を保証していない可能性があるため、このような種類のファイルを開かないでください (期待しない限り)。  <br/> ||

> [!TIP]
> ブロックするファイルをマルウェア対策の一覧に追加することもできます。マルウェア [から保護します](#protect-against-malware)。

詳細については、以下を参照してください。

- [ランサムウェア: リスクを軽減する方法](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [ベストな組み合わせ: Microsoft Defender ウイルス対策と Office 365](../../security/defender-endpoint/office-365-microsoft-defender-antivirus.md)

- [OneDrive を復元する](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)


## <a name="protect-sensitive-emails"></a>機密性の高いメールを保護する

Microsoft 365には、組織内外のユーザー間で暗号化された電子メール メッセージを送受信できるOfficeメッセージ暗号化が含まれており、目的の受信者のみが表示できます。 暗号化は、Outlook.com、Yahoo!、Gmail、およびその他の電子メール サービスで機能します。

> [!Tip]
> より厳しいセキュリティ レベルが必要な場合は、組織で電子メールまたはファイルの秘密度ラベル付けも構成して使用する必要があります。 [秘密度ラベル](../../compliance/sensitivity-labels.md) を使用すると、場所に関係なくコンテンツを制御できます。

### <a name="send-encrypted-email"></a>暗号化された電子メールを送信する

メールを暗号化するには:

1. 新しいメールを開いた状態で、[ **オプション]** メニューを選択します。
1. **[暗号化**] ドロップダウンから、適切なアクセス許可レベルを選択します。

:::image type="content" source="../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639b.png" alt-text="Outlookでの電子メール メッセージの暗号化":::

### <a name="receive-encrypted-email"></a>暗号化された電子メールを受信する

受信者が 2013 またはOutlook 2016 Outlookと Microsoft メール アカウントを持っている場合、閲覧ウィンドウにアイテムの制限付きアクセス許可に関するアラートが表示されます。 メッセージを開いた後、受信者は他のメッセージと同様にメッセージを表示できます。

受信者が Gmail や Yahoo などの別のメール クライアントまたはメール アカウントを使用している場合は、メール メッセージを読み取るためにサインインしたり、Web ブラウザーでメッセージを表示するためのワンタイム パスコードを要求したりするためのリンクが表示されます。 ユーザーがメールを受信していない場合は、迷惑メールフォルダーまたは迷惑メール フォルダーを確認する必要があります。

> [!TIP]
> 詳細については、「[PC 版 Outlook での暗号化されたメッセージの送信、表示、および返信](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)」を参照してください。

## <a name="protect-the-organization"></a>組織を保護する

Microsoft 365環境用に 1 つ以上のカスタム ドメインを構成した場合は、対象となるフィッシング対策保護を構成できます。 フィッシング対策保護はMicrosoft Defender for Office 365に含まれており、悪意のある偽装ベースのフィッシングやその他の攻撃から組織を保護するのに役立ちます。

> [!Note]
> カスタム ドメインを構成していない場合は、これを行う必要はありません。

最も重要なユーザーとカスタム ドメインのポリシーを作成して、この保護を開始することをお勧めします。 これを行うのに適した場所は、Microsoft Business プレミアムに含まれるMicrosoft 365 Defenderです。 Defender for Office 365でフィッシング対策ポリシーを作成するには、次の手順を実行します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動します。

2. [ポリシー **] セクションの [電子メール & コラボレーション** \> **ポリシー&ルール** \> **脅威ポリシー** \> **フィッシング対策**] に移動します。

3. [フィッシング対策] ページで、[ **+ 作成**] を選択します。 フィッシング対策ポリシーを定義する手順を示すウィザードが起動します。

4. ポリシーの名前、説明、および設定は、次の表で推奨されるように指定します。 詳細については、[Microsoft Defender for Office 365 オプションのフィッシング対策ポリシーの詳細に関するページを参照してください](../../security/office-365-security/set-up-anti-phishing-policies.md)。

5. 設定を確認したら、必要に応じて[**このポリシーの作成****] または [保存] を** 選択します。

|設定またはオプション|推奨される設定値|
|---|---|
|名前|ドメインと最も価値のあるキャンペーン スタッフ|
|説明|最も重要なスタッフとドメインが偽装されていないことを確認します。|
|保護対象のユーザーの追加|[ **+ 条件の追加]、[受信者] の順に選択します**。 ユーザー名を入力するか、候補者、キャンペーン マネージャー、その他の重要なスタッフ メンバーのメール アドレスを入力します。 偽装から保護する最大 20 個の内部アドレスと外部アドレスを追加できます。|
|保護対象のドメインの追加|[ **+ 条件の追加] を選択します。受信者ドメインは次です**。 Microsoft 365 サブスクリプションに関連付けられているカスタム ドメインを定義している場合は、そのドメインを入力します。 複数のドメインを入力できます。|
|処理の選択|偽装されたユーザーから電子メールが送信された場合: [ **別の電子メール アドレスにメッセージをリダイレクト** する] を選択し、セキュリティ管理者の電子メール アドレスを入力します。たとえば、securityadmin@contoso.com。 <br/> 偽装されたドメインによって電子メールが送信される場合は、[ **検疫メッセージ]** を選択します。|
|メールボックス インテリジェンス|既定では、新しいフィッシング対策ポリシーの作成時にはメールボックス インテリジェンスが選択されています。 最適な結果が得られるように、この設定は **[オン]** のままにしておいてください。|
|信頼できる送信者とドメインの追加|この例では、オーバーライドは定義しません。|
|適用先|**[受信者のドメインが次の場合]** を選択します。 **[これらのいずれか]** では、**[選択]** を選択します。 **[+ 追加]** を選択します。 一覧でドメインの名前の横にあるチェック ボックス (contoso.com など) を選択し、[ **追加**] を選択します。 **[完了]** を選択します。|

> [!TIP]
> 詳細については、「[Defender for Office 365でのフィッシング対策ポリシーの設定](../../security/office-365-security/configure-atp-anti-phishing-policies.md)」を参照してください。

## <a name="protect-against-malicious-attachments-files-and-urls"></a>悪意のある添付ファイル、ファイル、URL から保護する

ユーザーは、ドキュメント、プレゼンテーション、スプレッドシートなどの添付ファイルを定期的に送信、受信、共有します。 電子メール メッセージを見るだけで、添付ファイルが安全か悪意があるかを常に簡単に判断できるわけではありません。 Microsoft Defender for Office 365添付ファイル保護セーフ含まれていますが、この保護は既定では有効になりません。 この保護の使用を開始する新しいルールを作成することをお勧めします。 この保護は、SharePoint、OneDrive、およびMicrosoft Teams内のファイルに拡張されます。

### <a name="set-up-safe-attachments"></a>セーフ添付ファイルを設定する

添付ファイル ポリシーを事前に設定セーフ使用することも、独自のポリシーを作成することもできます。 セーフ添付ファイル ポリシーを作成するには、[短いトレーニング ビデオ](increase-threat-protection.md)を表示するか、次の手順を実行します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動し、管理者アカウントでサインインします。

2. [ポリシー **] セクション****の [電子メール & コラボレーション** \> **ポリシー&ルール** \> **脅威ポリシー** \> **マルウェア対策**] に移動します。

3. **+ 作成** を選択して新しいポリシーを作成します。

4. 次の表の設定を適用します。

5. 設定を確認したら、必要に応じて[**このポリシーの作成****] または [保存] を** 選択します。

|設定またはオプション|推奨される設定値|
|---|---|
|名前|検出されたマルウェアを使用して、現在および将来の電子メールをブロックします。|
|説明|検出されたマルウェアを使用して、現在および将来の電子メールと添付ファイルをブロックします。|
|添付ファイルの不明なマルウェア応答を保存する|[ **ブロック] - 検出されたマルウェアを含む現在および将来のメールと添付ファイルをブロック** します。|
|検出時に添付ファイルをリダイレクトする|リダイレクトを有効にする (このボックスを選択) <br/> 管理者アカウントまたは検疫用のメールボックスの設定を入力します。 <br/> 添付ファイルのマルウェア スキャンがタイムアウトまたはエラーが発生した場合は、上記の選択を適用します (このボックスを選択します)。|
|適用先|受信者ドメインは . . . ドメインを選択します。|

> [!TIP]
> 詳細については、「[Defender for Office 365でのフィッシング対策ポリシーの設定](../../security/office-365-security/configure-atp-anti-phishing-policies.md)」を参照してください。

### <a name="set-up-safe-links"></a>セーフ リンクを設定する

ハッカーは、電子メールや他のファイル内のリンクに悪意のある Web サイトを非表示にすることがあります。 Microsoft Defender for Office 365の一部である セーフ リンクは、電子メール メッセージとOfficeドキュメントで Web アドレス (URL) をクリックで確認する時間を提供することで、組織を保護するのに役立ちます。 保護は、セーフ リンク ポリシーを使用して定義されます。

攻撃から保護するには、次の操作を行います。

- 既定のポリシーを変更して保護を強化します。

- ドメイン内のすべての受信者を対象とする新しいポリシーを追加します。

リンクをセーフするには、[短いトレーニング ビデオ](increase-threat-protection.md#protect-against-phishing-attacks-with-safe-links)を表示するか、次の手順を実行します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>に移動し、管理者アカウントでサインインします。

2. [ポリシー **] セクション****の [電子メール & コラボレーション** \> **ポリシー&ルール** \> **脅威ポリシー** \> **マルウェア対策**] に移動します。

3. **[+ 作成]** を選択して新しいポリシーを作成するか、既定のポリシーを変更します。

既定のポリシーを変更するには:

1. **既定** のポリシーをダブルクリックします。 ポップアップが表示されます。 

2. ポップアップの下部にある [ **保護設定の編集]** を選択します。

3. 既定のポリシーを変更したら、[保存] を選択 **します**。

|設定またはオプション|推奨される設定値|
|---|---|
|名前|ドメイン内のすべての受信者に対するリンク ポリシーをセーフする|
|メッセージ内の悪意のある可能性のある不明な URL のアクションを選択する|[オン] を選択すると、 **ユーザーがリンクをクリックしたときに、URL が書き換えられ、既知の悪意のあるリンクの一覧に対してチェックされます**。|
|不審なリンクや、ファイルを指しているリンクに対してリアルタイム URL スキャンを適用します|このボックスを選択します。|
|適用先|受信者ドメインは . . . ドメインを選択します。|

> [!TIP]
> 詳細については、「[Microsoft Defender for Office 365のリンクのセーフ](../../security/office-365-security/atp-safe-links.md)」を参照してください。

## <a name="increase-protection-for-your-organizations-devices"></a>組織のデバイスの保護を強化する

Microsoft Defender ウイルス対策は、Windows オペレーティング システムに組み込まれており、ウイルスやマルウェアに対する優れた保護を提供します。 ただし、組織のデバイスの保護を強化するには、組織のような中小企業向けの新しいオファリングであり、Microsoft 365 Business Premiumに含まれる[Microsoft Defender for Business](../../business-premium/index.md)にオンボードします。 Defender for Business を使用すると、組織のデバイスはランサムウェア、マルウェア、フィッシング、その他の脅威から保護されます。

Microsoft 365 Business Premiumを使用すると、デバイス管理や高度な脅威保護などのセキュリティ機能が強化されます。 デバイスを Microsoft 365 Business for Defender に登録すると、デバイスは InTune によって監視および保護されます。


詳細については、次のリソースを参照してください。

- [Microsoft Defender for Businessの概要](../../security/defender-business/mdb-overview.md)

- [Microsoft Defender for Businessの設定と構成](../../security/defender-business/mdb-setup-configuration.md)

- [Microsoft 365 Defender ポータルを使用した概要](../../security/defender-business/mdb-get-started.md)

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365の多要素認証](multi-factor-authentication-microsoft-365.md) (記事)\
[優先度アカウントの管理と監視](../setup/priority-accounts.md) (記事)\
[管理センターでレポートをMicrosoft 365する](../activity-reports/activity-reports.md) (ビデオ)
