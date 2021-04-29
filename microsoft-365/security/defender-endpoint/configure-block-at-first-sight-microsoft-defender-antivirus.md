---
title: ブロックを一目で有効にしてマルウェアを数秒で検出する
description: 一目でブロックをオンにし、数秒でマルウェアを検出してブロックします。
keywords: スキャン、一目でブロックする、マルウェア、一目で見る、クラウド、ディフェンダー、ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079205"
---
# <a name="turn-on-block-at-first-sight"></a>事前ブロックを有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

この記事では、「一目でブロックする」と呼ばれるウイルス対策/マルウェア対策機能について説明し、組織で一目でブロックを有効にする方法について説明します。 

> [!TIP]
> この記事は、組織のセキュリティ設定を管理するエンタープライズ管理者と IT 管理者向けです。 enteprise 管理者または IT Pro ではないが、一目でブロックに関する質問がある場合は、「Not an enterprise admin or [IT Pro?](#not-an-enterprise-admin-or-it-pro)」を参照してください。

## <a name="what-is-block-at-first-sight"></a>"一目でブロック" とは何ですか?

一目でブロックする機能は、新しいマルウェアを検出し、数秒でブロックする次世代保護の脅威保護機能です。 特定のセキュリティ設定が有効になっている場合、一目でブロックが有効になります。 これらの設定には、次のものが含まれます。

- クラウドによる保護。 
- 指定したサンプル送信タイムアウト (50 秒など)。そして 
- ファイルブロックレベルが高い。 

ほとんどの企業組織では、ブロックを一目で有効にするために必要な設定は、Microsoft Defender Antivirus 展開で構成されます。 

## <a name="how-it-works"></a>しくみ

Microsoft Defender Antivirus が疑わしいが検出されないファイルを検出すると、クラウド保護バックエンドに対してクエリを実行します。 クラウド バックエンドは、ファイルのヒューリスティック、機械学習、および自動分析を適用して、ファイルが悪意のあるファイルであるかどうかを判断します。

Microsoft Defender Antivirus は、複数の検出および防止テクノロジを使用して、正確でインテリジェントでリアルタイムの保護を提供します。 

![Microsoft Defender AV エンジンの一覧](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> 詳細については、このブログを参照してください。 Microsoft Defender for Endpoint 次世代保護の中核となる高度なテクノロジ [について説明します](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。

## <a name="a-few-things-to-know-about-block-at-first-sight"></a>一目でブロックについて知る必要があります。

- Windows 10 バージョン 1803 以降では、一目でブロックすると、移植できない実行可能ファイル (JS、VBS、マクロなど) と実行可能ファイルをブロックできます。

- 一目でブロックすると、インターネットからダウンロードされた実行可能ファイル、またはインターネット ゾーンから発生するポータブルでない実行可能ファイルに対してクラウド保護バックエンドのみを使用します。 .exe ファイルのハッシュ値は、クラウド バックエンドを介してチェックされ、ファイルが以前に検出されていないファイルかどうかを判断します。

- クラウド バックエンドが判断できない場合、Microsoft Defender Antivirus はファイルをロックし、コピーをクラウドにアップロードします。 クラウドは、ファイルが悪意のあると判断したかどうかに応じて、ファイルを実行したり、すべての将来の遭遇でブロックしたりする前に、より多くの分析を実行して決定に到達します。

- 多くの場合、このプロセスでは、新しいマルウェアの応答時間を数時間から数秒に短縮できます。

- クラウドベースの [保護サービスが](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) ファイルを分析する間、ファイルの実行を妨げる時間を指定できます。 また、ファイル [がブロックされている場合に](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) ユーザーのデスクトップに表示されるメッセージをカスタマイズできます。 会社名、連絡先情報、メッセージ URL を変更できます。

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>Microsoft Intune で一目でブロックを有効にする

> [!TIP]
> Microsoft Intune は、Microsoft エンドポイント マネージャーの一部です。

1. Microsoft Endpoint Manager 管理センター ( ) で、[ [https://endpoint.microsoft.com](https://endpoint.microsoft.com) デバイス構成 **プロファイル**  >  **] に移動します**。

2. [デバイス制限] プロファイルの種類を使用 **してプロファイルを選択または** 作成します。

3. [デバイス制限 **プロファイルの** 構成設定] で **、[Microsoft Defender ウイルス** 対策] の下で次の設定を設定または確認します。

   - **クラウド配信の保護**: 有効
   - **ファイル ブロック レベル**: 高
   - **クラウドによるファイル スキャンの** 時間の延長 : 50
   - **サンプル提出の前にユーザーに確認** する : プロンプトを表示せずにすべてのデータを送信する

   ![Intune の構成](images/defender/intune-block-at-first-sight.png)

4. 設定内容を保存します。

> [!TIP]
> - ファイル ブロック レベルを High に設定 **すると** 、強力なレベルの検出が適用されます。 万が一、ファイルブロックによって正当なファイルが誤検知された場合、セキュリティ運用チームは検疫済みファイル [を復元できます](./restore-quarantined-files-microsoft-defender-antivirus.md)。
> - Intune で Microsoft Defender ウイルス対策デバイスの制限を構成する方法の詳細については、「Configure device Restriction [settings in Microsoft Intune」を参照してください](/intune/device-restrictions-configure)。
> - Intune の Microsoft Defender ウイルス対策デバイスの制限の一覧については、「Intune の Windows 10 (以降) のデバイス制限 [」を参照してください](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)。

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager で一目でブロックを有効にする

> [!TIP]
> Microsoft Endpoint Configuration Manager を探している場合は、Microsoft エンドポイント マネージャーの一部です。

1. Microsoft Endpoint Manager ( ) で [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、[エンドポイント セキュリティ **ウイルス対策] に**  >  **移動します**。

2. 既存のポリシーを選択するか、Microsoft Defender ウイルス対策プロファイルの種類を使用して新 **しいポリシーを** 作成します。

3. 次の構成設定を設定または確認します。

   - **クラウドによる保護を有効にする**: はい
   - **クラウドによって提供される保護レベル**: 高
   - **Defender Cloud Extended Timeout in Seconds**: 50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="エンドポイント マネージャーで一目で確認する設定をブロックする":::

4. すべてのユーザー、すべてのデバイス、またはすべてのユーザーとデバイスなどのグループにMicrosoft Defender ウイルス対策プロファイル **を適用します**。

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>グループ ポリシーで一目でブロックを有効にする

> [!NOTE]
> Intune または Microsoft エンドポイント マネージャーを使用して、一目でブロックを有効にすることをお勧めします。 

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。 

2. グループ ポリシー **管理エディターを使用して、[****コンピューターの構成] [** 管理用テンプレート  >    >  **] Windows コンポーネント Microsoft** Defender ウイルス対策マップ  >  **に**  >  **移動します**。 

3. [マップ] セクションで、[一目でブロックする] 機能を構成する **を** ダブルクリックし、[有効] に設定し **、[OK] を選択します**。

    > [!IMPORTANT]
    > 常に **プロンプト (0) に設定すると** 、デバイスの保護状態が低下します。 [送信 **しない] (2) に設定すると** 、一目でブロックが機能しません。

4. [マップ] セクションで、[詳細な分析が必要な場合にファイル サンプルを送信する] をダブルクリックし、[有効] に **設定します**。 [詳細 **な分析が必要な場合にファイル サンプルを送信する] で、[** すべての **サンプルを送信** する] を選択し **、[OK] を選択します**。

5. グループ ポリシー オブジェクトを、通常と同じ方法でネットワーク全体に再展開します。

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a>個々のクライアント デバイスでブロックが一目で有効になっているか確認する

Windows セキュリティ アプリを使用して、個々のクライアント デバイスでブロックが一目で有効になっているか確認できます。 クラウド配信の保護と自動サンプル送信の両方が有効になっている限り、一目で **ブロックが自動的** に有効になります。

1. Windows セキュリティ アプリを開きます。

2. [ **ウイルス対策&脅威保護]** を選択し、[ウイルスの検出] の [脅威&の設定] で **、[設定の管理**] **を選択します**。

   ![Windows セキュリティ アプリの [ウイルス&保護設定] ラベルのスクリーンショット](images/defender/wdav-protection-settings-wdsc.png)

3. クラウドによる **保護と自動** サンプル **送信の両方が** 有効になっていることを確認します。

> [!NOTE]
> - 前提条件の設定がグループ ポリシーを使用して構成および展開されている場合、このセクションで説明する設定はグレー表示され、個々のエンドポイントで使用できません。 
> - グループ ポリシー オブジェクトを使用して行った変更は、Windows の設定で設定を更新する前に、最初に個々のエンドポイントに展開する必要があります。

## <a name="validate-block-at-first-sight-is-working"></a>ブロックの一目での検証が機能している

機能が動作しているのを確認するには、「ネットワークとクラウド間の接続を検証する」 [のガイダンスに従います](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)。

## <a name="turn-off-block-at-first-sight"></a>一目でブロックをオフにする

> [!CAUTION]
> ブロックを一目でオフにすると、デバイスとネットワークの保護状態が低下します。

実際にブロックを一目で保護せずに前提条件の設定を保持する場合は、一目でブロックを無効にすることもできます。 一時的にブロックをオフにし、この機能がネットワークに与える影響を確認できます。 ただし、一目でブロックを完全に無効にすることをお勧めしません。

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager でブロックを一目でオフにする

1. Microsoft Endpoint Manager 管理センター ( ) に移動 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) し、サインインします。

2. [エンドポイント セキュリティ **ウイルス対策**  >  **] に** 移動し、Microsoft Defender ウイルス対策ポリシーを選択します。

3. [管理 **] で**、[プロパティ] **を選択します**。

4. [構成設定 **] の横にある**[編集] **を選択します**。

5. 次の設定の 1 つ以上を変更します。

   - [ **クラウド配信の保護を有効にする] を** **[いいえ] または [構成** されていません **] に設定します**。
   - [ **クラウド配信の保護レベル] を [** 構成されていません **] に設定します**。
   - [Defender Cloud **Extended Timeout in seconds] のチェック ボックスをオフにします**。

6. 設定を確認して保存します。

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>グループ ポリシーで一目でブロックをオフにする

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

2. グループ ポリシー管理 **エディターを使用して、[** コンピューターの構成] **に移動し、[** 管理 **用テンプレート] を選択します**。

3. Windows コンポーネントの Microsoft Defender ウイルス **対策**  >  マップを **通じてツリーを**  >  **展開します**。

4. [一目 **でブロックする] 機能をダブルクリックし、** オプションを [無効] に **設定します**。

    > [!NOTE]
    > 一目でブロックを無効にしても、前提条件のグループ ポリシーは無効または変更されない。

## <a name="not-an-enterprise-admin-or-it-pro"></a>エンタープライズ管理者または IT プロではありませんか?

エンタープライズ管理者または IT プロではないが、ブロックに関する質問がある場合は、このセクションを参照してください。 一目でブロックする機能は、数秒でマルウェアを検出してブロックする脅威保護機能です。 [一目でブロックする] という特定の設定は指定されていませんが、デバイスで特定の設定が構成されている場合、この機能は有効になります。

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a>自分のデバイスで一目でブロックを管理する方法

組織によって管理されていない個人用デバイスがある場合は、一目でブロックをオンまたはオフにする方法について疑問に思う場合があります。 Windows セキュリティ アプリを使用して、一目でブロックを管理できます。

1. Windows 10 コンピューターで、Windows セキュリティ アプリを開きます。

2. [ **ウイルス対策&を選択します**。

3. [ **ウイルス対策&の設定] で、[** 設定の管理 **] を選択します**。

4. 次のいずれかの手順を選択します。

   - 一目でブロックを有効にするには、クラウド配信の保護と自動サンプル送信の **両方** が有効になっていることを確認します。

   - 一目でブロックを無効にするには、[クラウド配信の保護] または [自動サンプル **送信****] をオフにします**。 <br/>
    
     > [!CAUTION]
     > ブロックを一目でオフにすると、デバイスの保護レベルが下がります。 一目でブロックを完全に無効にすることをお勧めしません。 


## <a name="see-also"></a>関連項目

- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
- [クラウドによる保護を有効にする](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Windows セキュリティで保護された環境を保つ](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)