---
title: ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法
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
description: ランサムウェア、フィッシング、悪意のある添付ファイルなどのサイバー脅威からビジネス メールとデータを保護します。
ms.openlocfilehash: 2e72ca635269000fe97a555390e7c65d39d2377e
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325699"
---
# <a name="top-10-ways-to-secure-microsoft-365-for-business-plans"></a>ビジネス プランのセキュリティをMicrosoft 365するトップ 10 の方法

Microsoft のビジネス プランのいずれかを使用している小規模または中規模の組織の場合は、この記事のガイダンスを使用して組織のセキュリティを強化できます。 このガイダンスは、組織が「ハーバード・ケネディ学校サイバーセキュリティ キャンペーン ハンドブック」に記載されている目標を [達成するのに役立ちます](https://go.microsoft.com/fwlink/p/?linkid=2015598)。

> [!TIP]
> この記事の手順に関するヘルプが必要な場合は、Microsoft の小規模ビジネス スペシャリストとの [作業を検討してください](https://go.microsoft.com/fwlink/?linkid=2186871)。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。

## <a name="watch-overview-of-security"></a>ウォッチ: セキュリティの概要

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mzxI?autoplay=false]

Microsoft 365 Business Premiumは、脅威保護、データ保護、デバイス管理機能を提供し、オンライン上の脅威や不正アクセスから企業を保護し、携帯電話、タブレット、およびコンピューター上の企業データを保護および管理するのに役立ちます。

## <a name="security-tasks-to-complete"></a>完了するセキュリティ タスク

Microsoft では、サービス プランに適用される次の表に示すタスクを完了してください。

|*数値*|タスク|Microsoft 365 Business Standard|Microsoft 365 Business Premium|
|---|---|---|---|
| 1 | [紛失または盗まれたパスワードから保護する](#1-set-up-multi-factor-authentication) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| 2 | [ユーザーをトレーニングする](#2-train-your-users) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| 3 | [専用の管理者アカウントを使用する](#3-use-dedicated-admin-accounts)|![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | 
| 4 | [マルウェアから保護する](#4-protect-against-malware) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(電子メールの保護) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(電子メールとデバイスの保護の強化) |
| 5 | [ランサムウェアから保護する](#5-protect-against-ransomware) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(電子メールとクラウド ストレージの保護) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(デバイス、電子メール、クラウド ストレージの保護の強化) |
| 6  | [電子メールの自動転送を停止する](#6-stop-auto-forwarding-for-email) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| 7  | [暗号化の使用](#7-use-office-message-encryption) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| 8  | [フィッシング攻撃からメールを保護する](#8-protect-your-email-from-phishing-attacks) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(アンチフィッシュ保護) | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(高度なアンチフィッシュ保護) |
| 9  | [電子メールおよびファイル内の悪意のある添付ファイル、ファイル、URL からOfficeする](#9-protect-against-malicious-attachments-files-and-urls) | | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(セーフリンクとセーフ添付ファイル) |
| 10 | [組織のデバイスの保護を強化する](#10-increase-protection-for-your-organizations-devices) | | ![含まれています。](../../media/d238e041-6854-4a78-9141-049224df0795.png) <br/>(エンタープライズ グレードのデバイス保護) |

Microsoft Business を使用しているプレミアム、セキュリティをセットアップし、安全に共同作業を開始する最も簡単な方法は、このライブラリのガイダンスに従[Microsoft 365 Business Premium。](../../business-premium/index.md) このガイダンスは、高度なハッカーによって起動されるサイバー脅威からすべての中小企業のお客様を保護するために、Microsoft Defending Democracy チームと提携して開発されました。

開始する前に、ポータル[Microsoft 365で](../../security/defender/microsoft-secure-score.md)セキュリティで保護されたスコアを<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderしてください</a>。 一元化されたダッシュボードから、ID、データ、アプリ、デバイス、インフラストラクチャMicrosoft 365のセキュリティを監視および改善できます。 推奨されるセキュリティ機能を構成したり、セキュリティ関連のタスク (レポートの表示など) を実行したり、サードパーティのアプリケーションやソフトウェアを使用して推奨事項に対処したりするためのポイントが与えられる。 Microsoft 製品とサービスの広範なセットに対する分析情報の追加と可視性の向上により、組織のセキュリティ正常性に関する自信を持って報告できます。

![Microsoft Secure Score のスクリーンショット。](../../media/secure-score.png)

## <a name="1-set-up-multi-factor-authentication"></a>1: 多要素認証を設定する

多要素認証 (MFA) を使用して、紛失または盗まれたパスワードから保護します。 多要素認証が設定されている場合、ユーザーは電話でコードを使用してユーザーにサインインする必要Microsoft 365。 この追加の手順では、ハッカーがパスワードを知っている場合にハッカーが引き継ぐのを防ぐ可能性があります。 

多要素認証は、2 段階認証とも呼ばれる。 ユーザーは、ほとんどのアカウントに 2 段階認証プロセスを簡単に追加できます 。たとえば、Google アカウントや Microsoft アカウントに簡単に追加できます。 個人用 Microsoft アカウントに [2 段階認証プロセスを追加する方法を次に示します](https://go.microsoft.com/fwlink/p/?linkid=2016403)。

ユーザー認証を使用しているMicrosoft 365、ユーザーが多要素認証を使用してログインする必要がある設定を追加します。 この変更を行った場合、ユーザーは次回ログインするときに、2 要素認証のために電話をセットアップするように求めるメッセージが表示されます。
MFA を設定する方法と、ユーザーがセットアップを完了する方法のトレーニング ビデオについては、「 [MFA](set-up-multi-factor-authentication.md) とユーザーセットアップのセットアップ」 [を参照してください](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)。

### <a name="to-set-up-multi-factor-authentication-you-turn-on-security-defaults"></a>多要素認証を設定するには、セキュリティの既定値を有効にします。

ほとんどの組織では、セキュリティの既定値は、サインイン セキュリティを高いレベルで提供します。 詳細については、[「セキュリティの既定値とは?」](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) を参照してください。

サブスクリプションが新しい場合は、セキュリティの既定値が自動的に有効になっている可能性があります。

Azure ポータル内の Azure Active Directory (Azure AD) の **プロパティ** ウィンドウで、セキュリティの既定値を有効または無効にします。

1. グローバル管理者の資格情報を使用して、[MIcrosoft 365 管理センター](https://admin.microsoft.com) にサインインします。

2. 左側のナビゲーションで、**[すべて表示]** を選択し、**[管理センター]** の **[Azure Active Directory]** を選択します。

3. 管理センター **でAzure Active Directoryプロパティ****を** > Azure Active Directory **します**。

4. ページの下部で、**[セキュリティの既定値の管理]** を選択します。

5. セキュリティの規定値を有効にするには **[はい]** を選び、セキュリティの規定値を無効にするには **[いいえ]** を選んで、**[保存]** を選択します。

組織に多要素認証を設定した後、ユーザーはデバイスに 2 段階認証を設定する必要があります。 詳細については、「2 段階認証[プロセスのセットアップ」を参照Microsoft 365](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)。

> [!TIP]
> 詳細と推奨事項については、「ユーザーの多要素認証を [設定する」を参照してください](set-up-multi-factor-authentication.md)。

## <a name="2-train-your-users"></a>2: ユーザーをトレーニングする

Harvard Kennedy School [Cybersecurity キャンペーン](https://go.microsoft.com/fwlink/p/?linkid=2015598) ハンドブックは、フィッシング攻撃を識別するためのユーザーのトレーニングなど、組織内のセキュリティ意識の強い文化を確立するための優れたガイダンスを提供します。

さらに、Microsoft では、ユーザーが「アカウントとデバイスをハッカーやマルウェアから保護する」で説明されているアクション [を実行するようにお勧めします](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6)。 それらの操作を次に示します。

- 強力なパスワードの使用

- デバイスの保護

- デバイス PC および Mac PC でのWindows 10機能の有効化

Microsoft では、次の記事で推奨されるアクションを実行して、ユーザーが個人の電子メール アカウントを保護することもできます。

- [Outlook.com メール アカウントの保護に役立つ](https://support.microsoft.com/office/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

- [2 段階認証で Gmail アカウントを保護する](https://go.microsoft.com/fwlink/p/?linkid=2015688&)

## <a name="3-use-dedicated-admin-accounts"></a>3: 専用の管理者アカウントを使用する

管理環境の管理に使用する管理Microsoft 365特権が含まれます。 これらは、ハッカーやサイバー攻撃者にとって貴重なターゲットです。 管理アカウントは管理にのみ使用します。 管理者は、通常の非管理用に個別のユーザー アカウントを持ち、ジョブ機能に関連付けられたタスクを完了するために必要な場合にのみ管理アカウントを使用する必要があります。 追加の推奨事項:

- 管理者アカウントも多要素認証用に設定してください。

- 管理者アカウントを使用する前に、関連のないブラウザー セッションとアプリ (個人用メール アカウントを含む) を閉じます。

- 管理タスクを完了した後は、必ずブラウザー セッションからログアウトします。

## <a name="4-protect-against-malware"></a>4: マルウェアから保護する

お使Microsoft 365環境には、マルウェアに対する保護が含まれます。 次の方法でマルウェア保護を強化できます。

- 特定の種類のファイルで添付ファイルをブロックする
- デバイスでのウイルス対策/マルウェア対策保護の使用

### <a name="block-attachments-with-certain-file-types"></a>特定のファイルの種類の添付ファイルをブロックする

マルウェアに一般的に使用されるファイルの種類を含む添付ファイルをブロックすることで、マルウェアの保護を強化できます。 電子メールでマルウェア保護を強化するには、短いトレーニング ビデオ [を表示](increase-threat-protection.md#raise-the-level-of-protection-against-malware-in-mail)するか、次の手順を実行します。

1. [セキュリティ Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">] ポータル</a> \>  \>  \>で、[ポリシー] セクション&ルール&マルウェア対策ポリシーをメールで送信する」**に移動** します。

2. [マルウェア対策 **] ページで** 、[既定] (既定 **) をダブルクリックします**。 ポップアップが表示されます。 

3. フライ **アウトの下部にある [** 保護設定の編集] を選択します。 

4. 次のページの [保護の **設定] で**、[共通の添付ファイルフィルターを有効にする] の横にある **チェック ボックスをオンにします**。 ブロックされているファイルの種類は、このオプションの直下に一覧表示されます。 ファイルの種類を追加または削除するには **、リストの** 最後にある [ファイルの種類のカスタマイズ] を選択します。 

5. **[保存]** を選択します。 

詳細については、「 [EOP でのマルウェア対策保護」を参照してください](../../security/office-365-security/anti-malware-protection.md)。

### <a name="use-antivirus-and-antimalware-protection"></a>ウイルス対策とマルウェア対策の保護を使用する

Microsoft Defender ウイルス対策強力なウイルス対策とマルウェア対策の保護を提供し、オペレーティング システムWindows組み込みです。

組織で次の情報を使用Microsoft 365 Business Premium、次のデバイス保護が追加されます。

- 次世代の保護

- ファイアウォール保護

- Web コンテンツ フィルタリング

これらの機能は、Microsoft Defender for Business に含まれており、2022 年 3 月 1 日から、Microsoft 365 Business Premium顧客に展開を開始します。 

[Microsoft Defender for Business の詳細については、「Microsoft Defender for Business」を参照してください](../../security/defender-business/mdb-overview.md)。

## <a name="5-protect-against-ransomware"></a>5: ランサムウェアから保護する

ランサムウェアは、ファイルを暗号化するか、コンピューター画面をロックすることで、データへのアクセスを制限します。 その後、データへのアクセスと引き換えに、通常はBitcoinのような暗号化の形で「身代金」を求め、被害者から金銭を強要しようとする。

電子メールがホストされている電子メールと、Microsoft 365に保存されているファイルに対するランサムウェア保護OneDrive。 ユーザーがMicrosoft 365 Business Premium、組織のデバイスに対する追加のランサムウェア保護を受け取る必要があります。

ランサムウェアから保護するには、1 つ以上のメール フロー ルールを作成して、ランサムウェアに一般的に使用されるファイル拡張子をブロックしたり、電子メールでこれらの添付ファイルを受け取るユーザーに警告したりします。 良い開始点は、次の 2 つのルールを作成する方法です。

- マクロを含む添付ファイルOffice開く前に、ユーザーに警告します。 ランサムウェアはマクロ内に隠される可能性があります。そのため、ユーザーに知らないユーザーからこれらのファイルを開かされないように警告します。

- ランサムウェアなどの悪意のあるコードを含む可能性のあるファイルの種類をブロックします。 まず、実行可能ファイルの一般的な一覧 (下の表に示す) から始めます。 組織でこれらの実行可能な種類を使用し、電子メールで送信される場合は、前のルールに追加します (ユーザーに警告を表示します)。

メール トランスポート ルールを作成するには、短いトレーニング ビデオ [を表示](increase-threat-protection.md#protect-against-ransomware)するか、次の手順を実行します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。

2. メール フロー **カテゴリで** 、[ルール] を **選択します**。

3. を選択 **+** し、[新 **しいルールを作成する] を選択します**。

4. ダイアログ ボックスの下部にある **** を選択して、オプションの完全なセットを表示します。

5. ルールごとに次の表の設定を適用します。 残りの設定は、変更しない限り、既定のままにします。

6. **[保存]** を選択します。
    
| Setting | ファイルの添付ファイルを開く前にユーザーにOfficeする | ランサムウェアなどの悪意のあるコードを含む可能性のあるファイルの種類をブロックする |
|:-----|:-----|:-----|
|名前  <br/> |ランサムウェア対策ルール: ユーザーに警告する  <br/> |ランサムウェア対策ルール: ファイルの種類をブロックする  <br/> |
|場合は、このルールを適用します。 . .  <br/> |任意の添付ファイル 。 . . ファイル拡張子が一致します。 . .  <br/> |任意の添付ファイル 。 . . ファイル拡張子が一致します。 . .  <br/> |
|単語または語句を指定する  <br/> |次のファイルの種類を追加します。  <br/> dotm、docm、xlsm、sltm、xla、xlam、xll、pptm、potm、ppam、ppsm、sldm  <br/> |次のファイルの種類を追加します。  <br/> ade, adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、hta、inf、ins、ins、job、js、jse、lnk、mda、mdb、mde、mdz、msc、msi、msp、mst、pcd、reg、sct、shs、url、vb、vbe、vbs、wsc、wsf、wsh、  <br/> |
|次の操作を行います。 . .  <br/> |免責事項の先頭に追加する  <br/> |メッセージをブロックします。 . . メッセージを拒否し、説明を含める  <br/> |
|メッセージ テキストを提供する  <br/> |これらの種類のファイルは、悪意のあるコードが含まれている可能性があります。送信者が安全を保証するものではありません。  <br/> ||
   
> [!TIP]
> [手順 4: マルウェアから保護する] で、ブロックするファイルをマルウェア対策リスト [に追加することもできます](#4-protect-against-malware)。

詳しくは、次のトピックを参照してください。

- [ランサムウェア: リスクを軽減する方法](https://www.microsoft.com/security/blog/2020/04/28/ransomware-groups-continue-to-target-healthcare-critical-services-heres-how-to-reduce-risk/)

- [ベストな組み合わせ: Microsoft Defender ウイルス対策と Office 365](../../security/defender-endpoint/office-365-microsoft-defender-antivirus.md)

- [OneDrive を復元する](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="6-stop-auto-forwarding-for-email"></a>6: 電子メールの自動転送を停止する

ユーザーのメールボックスにアクセスするハッカーは、メールを自動的に転送するメールボックスを構成することで、メールを削除できます。 この問題は、ユーザーの認識がなくても発生する可能性があります。 メール フロー ルールを構成することで、この問題を回避できます。

メール トランスポート ルールを作成するには、次の方法を実行します。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 管理センター</a>に移動します。

2. メール フロー **カテゴリで** 、[ルール] を **選択します**。

3. を選択 **+** し、[新 **しいルールを作成する] を選択します**。

4. ダイアログ **ボックスの下部** にある [その他のオプション] を選択して、オプションの完全なセットを表示します。

5. 次の表の設定を適用します。 これらの設定を変更しない限り、残りの設定は既定のままにします。

6. **[保存]** を選択します。

|Setting|外部ドメインへのメールの自動転送を拒否する|
|---|---|
|名前|外部ドメインへの電子メールの自動転送を防止する|
|... の場合は、このルールを適用します。|送信者 。 . . は外部/内部です。 . . 組織内|
|条件の追加|受信者 。 . . は外部/内部です。 . . 組織外|
|条件の追加|メッセージのプロパティ 。 . . メッセージの種類を含める。 . . 自動転送|
|次の ..を実行します。|メッセージをブロックします。 . . メッセージを拒否し、説明を含める。|
|メッセージ テキストを提供する|この組織外の電子メールの自動転送は、セキュリティ上の理由から防止されます。|

## <a name="7-use-office-message-encryption"></a>7: メッセージ暗号化Office使用する

Officeメッセージ暗号化は、メッセージ暗号化にMicrosoft 365。 既にセットアップされています。 [Office暗号化] を使用すると、組織内外のユーザー間で暗号化された電子メール メッセージを送受信できます。 Office 365 Message Encryption は、Outlook.com、Yahoo!、Gmail、およびその他のメール サービスで機能します。 メール メッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。

Officeメッセージ暗号化には、メールの送信時に次の 2 つの保護オプションがあります。

- 転送しない

- 暗号化

組織では、メールにラベルを適用するその他のオプション (機密など) を構成している場合があります。

### <a name="to-send-protected-email"></a>保護されたメールを送信するには

[pc Outlook] で、電子 **メールで [オプション**] を選択し、[アクセス許可] **を選択します**。

![電子メール メッセージの暗号化 (Outlook)。](../../media/08e90a7e-a2d2-41a4-bae9-0a46b4ce639a.png)

[Outlook.com] で、[メールで **保護]** を選択します。 既定の保護は [ **転送しない] です**。 これを暗号化に変更するには、[アクセス許可の暗号化 **の変更] を選択** \> **します**。

![Outlook.com での電子メール メッセージの暗号化。](../../media/329ccf50-f6b1-4fb8-b249-60b907a82b7e.png)

### <a name="to-receive-encrypted-email"></a>暗号化されたメールを受信するには

受信者に 2013 Outlook Outlook 2016 と Microsoft の電子メール アカウントがある場合は、[閲覧] ウィンドウにアイテムの制限付きアクセス許可に関する警告が表示されます。 メッセージを開く後、受信者は他のメッセージと同様にメッセージを表示できます。

受信者が Gmail や Yahoo などの別のメール クライアントまたはメール アカウントを使用している場合は、サインインして電子メール メッセージを読むか、Web ブラウザーでメッセージを表示するためのワンタイム パスコードを要求するリンクが表示されます。 ユーザーがメールを受信していない場合は、[迷惑メール] フォルダーまたは [迷惑メール] フォルダーを確認します。

> [!TIP]
> 詳細については、「[PC 版 Outlook での暗号化されたメッセージの送信、表示、および返信](https://support.microsoft.com/office/eaa43495-9bbb-4fca-922a-df90dee51980)」を参照してください。

## <a name="8-protect-your-email-from-phishing-attacks"></a>8. フィッシング攻撃からメールを保護する

ユーザー設定環境に 1 つ以上のカスタム ドメインを構成したMicrosoft 365フィッシング対策保護を構成できます。 Office 365 用 Microsoft Defender の一部であるフィッシング対策保護は、悪意のある偽装ベースのフィッシング攻撃や他のフィッシング攻撃から組織を保護するのに役立ちます。 カスタム ドメインを構成していない場合は、これを行う必要があります。

最も重要なユーザーとカスタム ドメインを保護するためのポリシーを作成して、この保護を開始することをお勧めします。

Defender for Office 365フィッシング対策ポリシーを作成するには、短いトレーニング ビデオを表示するか、[](increase-threat-protection.md#protect-your-email-from-phishing-attacks)以下の手順を実行します。

1. [ポータル] <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender移動します</a>。

2. [ポリシー] **セクション&[** \>  \>  \>&フィッシング対策のルール] の [メール とグループのポリシー]  **に移動** します。

3. [フィッシング対策] ページで、[+ 作成] **を選択します**。 ウィザードが起動し、フィッシング対策ポリシーを定義する手順を実行します。

4. 推奨されるポリシーの名前、説明、設定を以下のグラフで指定します。 詳細については、「Microsoft Defender のフィッシング対策ポリシーについて」を参照[してください。Office 365してください](../../security/office-365-security/set-up-anti-phishing-policies.md)。

5. 設定を確認した後、必要に応じて [このポリシー **を作成する** ] または [ **保存]** を選択します。

|設定またはオプション|推奨される設定値|
|---|---|
|名前|ドメインと最も価値のあるキャンペーン スタッフ|
|説明|最も重要なスタッフとドメインが偽装されていないか確認します。|
|保護対象のユーザーの追加|[ **+ 条件の追加] を選択します。受信者は次の値を使用します**。 ユーザー名を入力するか、候補者、キャンペーン マネージャー、その他の重要なスタッフ メンバーのメール アドレスを入力します。 偽装から保護する最大 20 の内部アドレスと外部アドレスを追加できます。|
|保護対象のドメインの追加|[ **+ 条件の追加] を選択します。受信者ドメインは次の値です**。 サブスクリプションを定義している場合は、Microsoft 365に関連付けられているカスタム ドメインを入力します。 複数のドメインを入力できます。|
|処理の選択|偽装ユーザーからメールが送信される場合は、[メッセージを別の電子メール アドレスにリダイレクトする] を選択し、セキュリティ管理者の電子メール アドレスを入力します。たとえば、securityadmin@contoso.com。 <br/> 偽装ドメインから電子メールが送信される場合は、[検疫メッセージ] **を選択します**。|
|メールボックス インテリジェンス|既定では、新しいフィッシング対策ポリシーの作成時にはメールボックス インテリジェンスが選択されています。 最適な結果が得られるように、この設定は **[オン]** のままにしておいてください。|
|信頼できる送信者とドメインの追加|この例では、オーバーライドは定義しません。|
|適用先|**[受信者のドメインが次の場合]** を選択します。 **[これらのいずれか]** では、**[選択]** を選択します。 **[+ 追加]** を選択します。 ドメインの名前の横にあるチェック ボックスをオンにします (たとえば、リスト contoso.com をクリックし、[追加] を選択 **します**。 **[完了]** を選択します。|

> [!TIP]
> 詳細については、「Defender [for Office 365」を参照してください](../../security/office-365-security/configure-atp-anti-phishing-policies.md)。

## <a name="9-protect-against-malicious-attachments-files-and-urls"></a>9: 悪意のある添付ファイル、ファイル、URL から保護する

ドキュメント、プレゼンテーション、スプレッドシートなどの添付ファイルを定期的に送信、受信、共有します。 電子メール メッセージを見ただけで、添付ファイルが安全か悪意かを判断するのは必ずしも簡単ではありません。 Microsoft Defender for Office 365添付セーフが含まれていますが、この保護は既定では有効にされません。 この保護の使用を開始するには、新しいルールを作成することをお勧めします。 この保護は、SharePoint、OneDrive、およびMicrosoft Teams。

### <a name="set-up-safe-attachments"></a>添付ファイルのセーフ設定

添付ファイル ポリシーをセーフ、短いトレーニング ビデオ[を表示](increase-threat-protection.md)するか、次の手順を実行します。

1. [ポータル] <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderし</a>、管理者アカウントでサインインします。

2. [ポリシー] **セクション&[** \>  \>  \>&マルウェア対策ポリシー] に **移動** します。

3. [ **+ 作成] を選択** して新しいポリシーを作成します。

4. 次の表の設定を適用します。

5. 設定を確認した後、必要に応じて [このポリシー **を作成する** ] または [ **保存]** を選択します。

|設定またはオプション|推奨される設定値|
|---|---|
|名前|検出されたマルウェアを使用して、現在および将来のメールをブロックします。|
|説明|検出されたマルウェアを使用して、現在および将来の電子メールと添付ファイルをブロックします。|
|添付ファイルの不明なマルウェアの応答を保存する|[ **ブロック] を選択します。 検出** されたマルウェアを含む現在および将来のメールと添付ファイルをブロックします。|
|検出時に添付ファイルをリダイレクトする|リダイレクトを有効にする (このボックスを選択) <br/> 検疫用の管理者アカウントまたはメールボックスのセットアップを入力します。 <br/> 添付ファイルのマルウェア スキャンが時間切れまたはエラーが発生した場合は、上記の選択項目を適用します (このボックスを選択します)。|
|適用先|受信者ドメインはです。 . . ドメインを選択します。|

> [!TIP]
> 詳細については、「Defender [for Office 365」を参照してください](../../security/office-365-security/configure-atp-anti-phishing-policies.md)。

### <a name="set-up-safe-links"></a>リンクのセーフ設定

ハッカーは、メールや他のファイルのリンクに悪意のある Web サイトを非表示にしている場合があります。 セーフ Office 365 用 Microsoft Defender の一部であるリンクは、電子メール メッセージおよび Office ドキュメントで Web アドレス (URL) のクリック時検証を提供することで、組織を保護するのに役立ちます。 保護は、リンク ポリシーセーフによって定義されます。

攻撃から保護するには、次の手順を実行します。

- 保護を強化するために既定のポリシーを変更します。

- ドメイン内のすべての受信者を対象とする新しいポリシーを追加します。

[リンク] をセーフ、短いトレーニング ビデオ[を表示](increase-threat-protection.md#protect-against-phishing-attacks-with-safe-links)するか、次の手順を実行します。

1. [ポータル] <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defenderし</a>、管理者アカウントでサインインします。

2. [ポリシー] **セクション&[** \>  \>  \>&マルウェア対策ポリシー] に **移動** します。

3. [ **+ 作成]** を選択して新しいポリシーを作成するか、既定のポリシーを変更します。

既定のポリシーを変更するには、次のコマンドを実行します。

1. [既定のポリシー] **をダブルクリック** します。 ポップアップが表示されます。 

2. フライ **アウトの下部にある [** 保護設定の編集] を選択します。

3. 既定のポリシーを変更した後、[保存] を **選択します**。

|設定またはオプション|推奨される設定値|
|---|---|
|名前|セーフのすべての受信者のリンク ポリシー|
|メッセージ内の不明な潜在的に悪意のある URL のアクションを選択する|[オン] を選択すると、ユーザーがリンクをクリックすると、URL が書き換えされ、既知の悪意のあるリンクの一覧 **に対してチェックされます**。|
|ファイルを指す疑わしいリンクやリンクに対してリアルタイムの URL スキャンを適用する|このボックスを選択します。|
|適用先|受信者ドメインはです。 . . ドメインを選択します。|

> [!TIP]
> 詳細については、「[Microsoft Defender セーフリンク」を参照Office 365](../../security/office-365-security/atp-safe-links.md)。

## <a name="10-increase-protection-for-your-organizations-devices"></a>10: 組織のデバイスの保護を強化する

Microsoft Defender ウイルス対策オペレーティング システムに組み込Windowsウイルスやマルウェアに対する優れた保護を提供します。 ただし、組織のデバイスを Microsoft Defender for Business にオンボーディングすることで、組織のデバイスの保護を強化できます。 Defender for Business を使用すると、組織のデバイスはランサムウェア、マルウェア、フィッシング、その他の脅威から保護されます。

**2022 年 3 月 1 日から、[Microsoft Defender for Business](../../security/defender-business/index.yml)** の機能が新しいMicrosoft 365 Business Premium。 


詳細については、次のリソースを参照してください。

- [Microsoft Defender for Business の概要](../../security/defender-business/mdb-overview.md)

- [Microsoft Defender for Business のセットアップと構成](../../security/defender-business/mdb-setup-configuration.md)

- [ポータルの使用Microsoft 365 Defenderする](../../security/defender-business/mdb-get-started.md)

## <a name="related-content"></a>関連コンテンツ

[ユーザーの多要素認証 (Microsoft 365](multi-factor-authentication-microsoft-365.md))\
[優先度アカウントの管理と監視](../setup/priority-accounts.md) (記事)\
[Microsoft 365センターの [レポート]](../activity-reports/activity-reports.md) (ビデオ)