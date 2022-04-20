---
title: ビジネス プランのMicrosoft 365をセキュリティで保護する上位 10 の方法
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
ms.openlocfilehash: 0e09b245d084b946596c61f9e760b56baed6043d
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/19/2022
ms.locfileid: "64935919"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>ビジネス プランのMicrosoft 365をセキュリティで保護する上位 10 の方法

Microsoft のビジネス プランのいずれかを使用している小規模または中規模の組織の場合は、この記事のガイダンスを使用して組織のセキュリティを強化できます。 このガイダンスは、組織が「中立大学ケネディ学校 [サイバーセキュリティ キャンペーン の手引き」](https://go.microsoft.com/fwlink/p/?linkid=2015598)に記載されている目標を達成するのに役立ちます。

> [!TIP]
> この記事の手順に関するヘルプが必要な場合は、 [Microsoft の小規模ビジネス スペシャリストと連携](https://go.microsoft.com/fwlink/?linkid=2186871)することを検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。

## <a name="watch-overview-of-security"></a>ウォッチ: セキュリティの概要

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mzxI?autoplay=false]

Microsoft 365 Business Premiumは、脅威保護、データ保護、デバイス管理機能を提供し、オンラインの脅威や不正アクセスから会社を保護し、携帯電話、タブレット、コンピューターで会社のデータを保護および管理するのに役立ちます。

## <a name="security-tasks-to-complete"></a>完了するセキュリティ タスク

サービス プランに適用される次の表に示すタスクを完了することをお勧めします。

|*数値*|タスク|Microsoft 365 Business Standard|Microsoft 365 Business Premium|
|---|---|---|---|
| 1 | [パスワードの紛失または盗難から保護する](#1-set-up-multi-factor-authentication) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| 2 | [ユーザーをトレーニングする](#2-train-your-users) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| 3 | [専用の管理者アカウントを使用する](#3-use-dedicated-admin-accounts)|![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | 
| 4 | [マルウェアから保護する](#4-protect-against-malware) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(電子メールの保護) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(電子メールとデバイスの保護の強化) |
| 5 | [ランサムウェアから保護する](#5-protect-against-ransomware) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(電子メールとクラウド ストレージの保護) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(デバイス、電子メール、クラウド ストレージの保護の強化) |
| 6  | [電子メールの自動転送を停止する](#6-stop-auto-forwarding-for-email) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| 7  | [メッセージ暗号化を使用する](#7-use-microsoft-purview-message-encryption) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| 8  | [フィッシング攻撃からメールを保護する](#8-protect-your-email-from-phishing-attacks) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(改ざん防止保護) | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(高度な改ざん防止保護) |
| 9  | [メール ファイルとOffice ファイル内の悪意のある添付ファイル、ファイル、URL から保護する](#9-protect-against-malicious-attachments-files-and-urls) | | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(セーフ リンクと添付ファイルセーフ) |
| 10 | [組織のデバイスの保護を強化する](#10-increase-protection-for-your-organizations-devices) | | ![含ま。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(エンタープライズ グレードのデバイス保護) |

Microsoft Business プレミアムをお持ちであれば、セキュリティをセットアップし、安全に共同作業を開始する最も簡単な方法は、このライブラリのガイダンス[に従Microsoft 365 Business Premium](../../business-premium/index.md)。 このガイダンスは、高度なハッカーによって起動されたサイバー脅威からすべての中小企業のお客様を保護するために、Microsoft 防御デモクラシー チームと協力して開発されました。

開始する前に、Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">ポータル</a>で[Microsoft 365セキュリティ](../../security/defender/microsoft-secure-score.md)スコアを確認します。 一元化されたダッシュボードから、Microsoft 365 ID、データ、アプリ、デバイス、インフラストラクチャのセキュリティを監視および向上させることができます。 推奨されるセキュリティ機能の構成、セキュリティ関連のタスクの実行 (レポートの表示など)、サード パーティ製のアプリケーションまたはソフトウェアを使用した推奨事項への対処に関するポイントが与えられます。 より広範な Microsoft 製品とサービスのセットに対する分析情報と可視性を高め、組織のセキュリティ正常性に関する自信を持って報告できます。

![Microsoft セキュリティ スコアのスクリーンショット。](../../media/secure-score.png)

## <a name="1-set-up-multi-factor-authentication"></a>1: 多要素認証を設定する

多要素認証 (MFA) を使用して、パスワードの紛失や盗難から保護します。 多要素認証が設定されている場合、ユーザーは携帯電話のコードを使用してMicrosoft 365にサインインする必要があります。 この追加の手順では、ハッカーがパスワードを知っている場合に引き継ぐのを防ぐことができます。 

多要素認証は、2 段階認証とも呼ばれます。 個人は、Google や Microsoft アカウントなど、ほとんどのアカウントに 2 段階認証を簡単に追加できます。 [個人用 Microsoft アカウントに 2 段階認証を追加する方法を次に示します](https://go.microsoft.com/fwlink/p/?linkid=2016403)。

Microsoft 365を使用している企業の場合は、ユーザーが多要素認証を使用してログインする必要がある設定を追加します。 この変更を行うと、ユーザーは次回ログインするときに、2 要素認証用に電話を設定するように求められます。
MFA を設定する方法とユーザーがセットアップを完了する方法に関するトレーニング ビデオについては、「MFA と[ユーザーのセットアップ](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)の[設定](set-up-multi-factor-authentication.md)」を参照してください。

### <a name="to-set-up-multi-factor-authentication-you-turn-on-security-defaults"></a>多要素認証を設定するには、セキュリティの既定値を有効にします

ほとんどの組織では、セキュリティの既定値により、適切なレベルのサインイン セキュリティが追加されます。 詳細については、[「セキュリティの既定値とは?」](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) を参照してください。

サブスクリプションが新しい場合は、セキュリティの既定値が自動的に有効になっている可能性があります。

Azure ポータル内の Azure Active Directory (Azure AD) の **プロパティ** ウィンドウで、セキュリティの既定値を有効または無効にします。

1. グローバル管理者の資格情報を使用して、[MIcrosoft 365 管理センター](https://admin.microsoft.com) にサインインします。

2. 左側のナビゲーションで、**[すべて表示]** を選択し、**[管理センター]** の **[Azure Active Directory]** を選択します。

3. **Azure Active Directory管理センター** で、**Azure Active Directory** >  **Properties** を選択します。

4. ページの下部で、**[セキュリティの既定値の管理]** を選択します。

5. セキュリティの規定値を有効にするには **[はい]** を選び、セキュリティの規定値を無効にするには **[いいえ]** を選んで、**[保存]** を選択します。

組織に多要素認証を設定した後、ユーザーはデバイスに 2 段階認証を設定する必要があります。 詳細については、「[Microsoft 365の 2 段階認証を設定する」を](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)参照してください。

> [!TIP]
> 詳細と推奨事項については、「 [ユーザーの多要素認証を設定する」を](set-up-multi-factor-authentication.md)参照してください。

## <a name="2-train-your-users"></a>2: ユーザーをトレーニングする

「中立大学ケネディ学校 [サイバーセキュリティ キャンペーン の手引き」](https://go.microsoft.com/fwlink/p/?linkid=2015598) では、フィッシング攻撃を特定するためのユーザーのトレーニングなど、組織内のセキュリティ意識の強い文化を確立するための優れたガイダンスを提供します。

さらに、Microsoft では、ユーザーが「 [ハッカーやマルウェアからアカウントとデバイスを保護](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6)する」に記載されているアクションを実行することをお勧めします。 それらの操作を次に示します。

- 強力なパスワードを使用する

- デバイスの保護

- Windows 10 PC と Mac PC でセキュリティ機能を有効にする

また、Microsoft では、次の記事で推奨されるアクションを実行して、ユーザーが個人用メール アカウントを保護することをお勧めします。

- [Outlook.com メール アカウントを保護する](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [2 段階認証で Gmail アカウントを保護する](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="3-use-dedicated-admin-accounts"></a>3: 専用の管理者アカウントを使用する

Microsoft 365環境の管理に使用する管理アカウントには、管理者特権が含まれます。 これらは、ハッカーやサイバー攻撃の貴重なターゲットです。 管理者アカウントは、管理にのみ使用します。 管理者は、通常の非管理者用の別のユーザー アカウントを持ち、自分のジョブ機能に関連付けられたタスクを完了するために必要な場合にのみ管理アカウントを使用する必要があります。 追加の推奨事項:

- 多要素認証用に管理者アカウントも設定されていることを確認します。

- 管理者アカウントを使用する前に、個人用メール アカウントを含め、無関係なすべてのブラウザー セッションとアプリを閉じます。

- 管理者タスクを完了したら、必ずブラウザー セッションからログアウトしてください。

## <a name="4-protect-against-malware"></a>4: マルウェアから保護する

Microsoft 365環境には、マルウェアに対する保護が含まれています。 次の方法でマルウェア保護を強化できます。

- 特定の種類のファイルを含む添付ファイルをブロックする
- デバイスでのウイルス対策/マルウェア対策保護の使用

### <a name="block-attachments-with-certain-file-types"></a>特定の種類のファイルを含む添付ファイルをブロックする

マルウェアの保護を強化するには、マルウェアでよく使用されるファイルの種類を含む添付ファイルをブロックします。 メールでマルウェア保護を強化するには、 [短いトレーニング ビデオ](increase-threat-protection.md#raise-the-level-of-protection-against-malware-in-mail)を表示するか、次の手順を実行します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender ポータル</a>で、[ポリシー **] セクション****の [電子メール & コラボレーション** \> **ポリシー&ルール** \> **脅威ポリシー** \> **マルウェア対策**] に移動します。

2. [ **マルウェア対策** ] ページで、[ **既定] (既定)** をダブルクリックします。 ポップアップが表示されます。 

3. ポップアップの下部にある [ **保護設定の編集]** を選択します。 

4. 次のページの [ **保護の設定**] で、[ **共通の添付ファイル フィルターを有効にする]** の横にあるチェック ボックスをオンにします。 ブロックされているファイルの種類は、このオプションのすぐ下に一覧表示されます。 ファイルの種類を追加または削除するには、リストの末尾にある **[ファイルの種類のカスタマイズ** ] を選択します。 

5. **[保存]** を選択します。 

詳細については、「 [EOP でのマルウェア対策保護](../../security/office-365-security/anti-malware-protection.md)」を参照してください。

### <a name="use-antivirus-and-antimalware-protection"></a>ウイルス対策とマルウェア対策の保護を使用する

Microsoft Defender ウイルス対策は強力なウイルス対策とマルウェア対策を提供し、Windows オペレーティング システムに組み込まれています。

組織でMicrosoft 365 Business Premiumを使用している場合は、次を含む追加のデバイス保護が提供されます。

- 次世代の保護

- ファイアウォール保護

- Web コンテンツ フィルタリング

これらの機能は、2022 年 3 月 1 日以降、Microsoft 365 Business Premiumのお客様へのロールアウトを開始するオファリングであるMicrosoft Defender for Businessに含まれています。 

[Microsoft Defender for Businessの詳細については、こちらを参照してください](../../security/defender-business/mdb-overview.md)。

## <a name="5-protect-against-ransomware"></a>5: ランサムウェアから保護する

ランサムウェアは、ファイルを暗号化したり、コンピューター画面をロックしたりすることで、データへのアクセスを制限します。 その後、データへのアクセスと引き換えに、通常はビットコインなどの仮想通貨の形式で"身代金" を求めることによって、被害者からお金を強要しようとします。

Microsoft 365でホストされている電子メールと、OneDriveに格納されているファイルに対してランサムウェア保護を受ける。 Microsoft 365 Business Premiumがある場合は、組織のデバイスに対して追加のランサムウェア保護を受けることができます。

ランサムウェアから保護するには、ランサムウェアでよく使用されるファイル拡張子をブロックする 1 つ以上のメール フロー ルールを作成するか、電子メールでこれらの添付ファイルを受信したユーザーに警告します。 適切な開始点は、次の 2 つのルールを作成することです。

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
> 「 [手順 4: マルウェアから保護](#4-protect-against-malware)する」のマルウェア対策リストに、ブロックするファイルを追加することもできます。

詳細については、以下を参照してください。

- [ランサムウェア: リスクを軽減する方法](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [ベストな組み合わせ: Microsoft Defender ウイルス対策と Office 365](../../security/defender-endpoint/office-365-microsoft-defender-antivirus.md)

- [OneDrive を復元する](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="6-stop-auto-forwarding-for-email"></a>6: 電子メールの自動転送を停止する

ユーザーのメールボックスにアクセスするハッカーは、電子メールを自動的に転送するようにメールボックスを構成することで、メールを流出させることができます。 この問題は、ユーザーの認識がなくても発生する可能性があります。 メール フロー ルールを構成することで、これを防ぐことができます。

メール トランスポート ルールを作成するには:

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。

2. **メール フロー** カテゴリで、**ルール** を選択します。

3. を選択 **+** し、 **新しいルールを作成します**。

4. ダイアログ ボックスの下部にある **[その他のオプション** ] を選択すると、オプションの完全なセットが表示されます。

5. 次の表の設定を適用します。 これらの設定を変更する場合を除き、残りの設定は既定のままにしておきます。

6. **[保存]** を選択します。

|Setting|外部ドメインへの電子メールの自動転送を拒否する|
|---|---|
|名前|外部ドメインへの電子メールの自動転送を防止する|
|... の場合は、この規則を適用します。|送信者 . . . は外部/内部です。 . . 組織内|
|条件を追加する|受信者 . . . は外部/内部です。 . . 組織外|
|条件を追加する|メッセージのプロパティ。 . . メッセージの種類を含めます。 . . 自動転送|
|次の操作を行います。..|メッセージをブロックします。 . . メッセージを拒否し、説明を含めます。|
|メッセージ テキストを指定する|セキュリティ上の理由から、この組織外の電子メールの自動転送は防止されます。|

## <a name="7-use-microsoft-purview-message-encryption"></a>7: Microsoft Purview メッセージ暗号化を使用する

Microsoft Purview メッセージ暗号化は、Microsoft 365に含まれています。 既に設定されています。 Microsoft Purview Message Encryption を使用すると、組織は組織内外のユーザー間で暗号化された電子メール メッセージを送受信できます。 Microsoft Purview Message Encryption は、Outlook.com、Yahoo!、Gmail、およびその他の電子メール サービスと連携します。 メール メッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。

Microsoft Purview Message Encryption には、メールの送信時に次の 2 つの保護オプションが用意されています。

- 転送しない

- 暗号化

組織で、ラベルを電子メールに適用する他のオプション (社外秘など) を構成している可能性があります。

### <a name="to-send-protected-email"></a>保護された電子メールを送信するには

PC のOutlookで、電子メールで **[オプション]** を選択し、[**アクセス許可**] を選択します。

![Outlookでの電子メール メッセージの暗号化。](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)

Outlook.com で、電子メールで **[保護**] を選択します。 既定の保護は **[転送しない] です**。 これを暗号化に変更するには、[**アクセス許可**\>の暗号化の変更] を選択 **します**。

![Outlook.com での電子メール メッセージの暗号化。](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)

### <a name="to-receive-encrypted-email"></a>暗号化された電子メールを受信するには

受信者が 2013 またはOutlook 2016 Outlookと Microsoft メール アカウントを持っている場合、閲覧ウィンドウにアイテムの制限付きアクセス許可に関するアラートが表示されます。 メッセージを開いた後、受信者は他のメッセージと同様にメッセージを表示できます。

受信者が Gmail や Yahoo などの別のメール クライアントまたはメール アカウントを使用している場合は、メール メッセージを読み取るためにサインインしたり、Web ブラウザーでメッセージを表示するためのワンタイム パスコードを要求したりするためのリンクが表示されます。 ユーザーがメールを受信していない場合は、迷惑メールフォルダーまたは迷惑メール フォルダーを確認します。

> [!TIP]
> 詳細については、「[PC 版 Outlook での暗号化されたメッセージの送信、表示、および返信](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)」を参照してください。

## <a name="8-protect-your-email-from-phishing-attacks"></a>8. フィッシング攻撃からメールを保護する

Microsoft 365環境用に 1 つ以上のカスタム ドメインを構成した場合は、対象となるフィッシング対策保護を構成できます。 Microsoft Defender for Office 365の一部であるフィッシング対策保護は、悪意のある偽装ベースのフィッシング攻撃やその他のフィッシング攻撃から組織を保護するのに役立ちます。 カスタム ドメインを構成していない場合は、これを行う必要はありません。

最も重要なユーザーとカスタム ドメインを保護するポリシーを作成して、この保護を開始することをお勧めします。

Defender for Office 365でフィッシング対策ポリシーを作成するには、[短いトレーニング ビデオ](increase-threat-protection.md#protect-your-email-from-phishing-attacks)を表示するか、次の手順を実行します。

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
|適用先|**[受信者のドメインが次の場合]** を選択します。 **[これらのいずれか]** では、**[選択]** を選択します。 **[+ 追加]** を選択します。 一覧でドメインの名前の横にあるチェック ボックス (contoso.com など) を選択し、[ **追加**] を選択します。 [**完了**] を選択します。|

> [!TIP]
> 詳細については、「[Defender for Office 365でのフィッシング対策ポリシーの設定](../../security/office-365-security/configure-atp-anti-phishing-policies.md)」を参照してください。

## <a name="9-protect-against-malicious-attachments-files-and-urls"></a>9: 悪意のある添付ファイル、ファイル、URL から保護する

ユーザーは、ドキュメント、プレゼンテーション、スプレッドシートなどの添付ファイルを定期的に送信、受信、共有します。 電子メール メッセージを見るだけで、添付ファイルが安全か悪意があるかを常に簡単に判断できるわけではありません。 Microsoft Defender for Office 365添付ファイル保護セーフ含まれていますが、この保護は既定では有効になりません。 この保護の使用を開始する新しいルールを作成することをお勧めします。 この保護は、SharePoint、OneDrive、およびMicrosoft Teams内のファイルに拡張されます。

### <a name="set-up-safe-attachments"></a>セーフ添付ファイルを設定する

セーフ添付ファイル ポリシーを作成するには、[短いトレーニング ビデオ](increase-threat-protection.md)を表示するか、次の手順を実行します。

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
|ファイルを指す不審なリンクとリンクのリアルタイム URL スキャンを適用する|このボックスを選択します。|
|適用先|受信者ドメインは . . . ドメインを選択します。|

> [!TIP]
> 詳細については、「[Microsoft Defender for Office 365のリンクのセーフ](../../security/office-365-security/atp-safe-links.md)」を参照してください。

## <a name="10-increase-protection-for-your-organizations-devices"></a>10: 組織のデバイスの保護を強化する

Microsoft Defender ウイルス対策は、Windows オペレーティング システムに組み込まれており、ウイルスやマルウェアに対する優れた保護を提供します。 ただし、組織のデバイスをMicrosoft Defender for Businessにオンボードすることで、組織のデバイスの保護を強化できます。 Defender for Business を使用すると、組織のデバイスはランサムウェア、マルウェア、フィッシング、その他の脅威から保護されます。

**2022 年 3 月 1 日以降、[Microsoft Defender for Business](../../security/defender-business/index.yml)機能がMicrosoft 365 Business Premiumに追加されます**。 


詳細については、次のリソースを参照してください。

- [Microsoft Defender for Business の概要](../../security/defender-business/mdb-overview.md)

- [Microsoft Defender for Businessの設定と構成](../../security/defender-business/mdb-setup-configuration.md)

- [Microsoft 365 Defender ポータルを使用した概要](../../security/defender-business/mdb-get-started.md)

## <a name="related-content"></a>関連コンテンツ

[Microsoft 365の多要素認証](multi-factor-authentication-microsoft-365.md) (記事)\
[優先度アカウントの管理と監視](../setup/priority-accounts.md) (記事)\
[管理センターでレポートをMicrosoft 365する](../activity-reports/activity-reports.md) (ビデオ)