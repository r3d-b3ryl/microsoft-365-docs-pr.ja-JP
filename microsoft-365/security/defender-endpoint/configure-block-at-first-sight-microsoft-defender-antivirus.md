---
title: ブロックを一目で有効にしてマルウェアを数秒で検出する
description: 一目でブロックをオンにし、数秒でマルウェアを検出してブロックします。
keywords: スキャン, BAFS, マルウェア, 最初に見た, 一目, クラウド, ディフェンダー
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 1baa770da677ec755bd56db9b92c071680efae7b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765757"
---
# <a name="turn-on-block-at-first-sight"></a>一目でブロックをオンにする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

一目でブロックすると、数秒で新しいマルウェアを検出してブロックできます。 この保護は、特定の前提条件設定が有効になっている場合、既定で有効になります。 これらの設定には、クラウド配信の保護、指定されたサンプル送信タイムアウト (50 秒など)、およびファイルブロック レベルの高が含まれます。 ほとんどのエンタープライズ組織では、Microsoft Defender ウイルス対策の展開でこれらの設定が既定で有効になっています。 

クラウドベースの [保護サービスが](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) ファイルを分析する間、ファイルの実行を妨げる時間を指定できます。 また、ファイル [がブロックされている場合に](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) ユーザーのデスクトップに表示されるメッセージをカスタマイズできます。 会社名、連絡先情報、メッセージ URL を変更できます。

>[!TIP]
>Microsoft Defender for Endpoint のデモ web サイトに [アクセスして](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com 機能が動作し、動作を確認します。

## <a name="how-it-works"></a>メカニズム

Microsoft Defender Antivirus が疑わしいが検出されないファイルを検出すると、クラウド保護バックエンドに対してクエリを実行します。 クラウド バックエンドは、ファイルのヒューリスティック、機械学習、および自動分析を適用して、ファイルが悪意のあるファイルであるかどうかを判断します。

Microsoft Defender Antivirus は、複数の検出および防止テクノロジを使用して、正確でインテリジェントでリアルタイムの保護を提供します。 詳細については、このブログを参照してください。 Microsoft Defender for Endpoint 次世代保護の中核となる高度なテクノロジ [について説明します](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)。
![Microsoft Defender AV エンジンの一覧](images/microsoft-defender-atp-next-generation-protection-engines.png)  

Windows 10 バージョン 1803 以降では、一目でブロックすると、移植できない実行可能ファイル (JS、VBS、マクロなど) と実行可能ファイルをブロックできます。

一目でブロックすると、インターネットからダウンロードされた実行可能ファイル、またはインターネット ゾーンから発生するポータブルでない実行可能ファイルに対してクラウド保護バックエンドのみを使用します。 .exe ファイルのハッシュ値は、クラウド バックエンドを介してチェックされ、ファイルが以前に検出されていないファイルかどうかを判断します。

クラウド バックエンドが判断できない場合、Microsoft Defender Antivirus はファイルをロックし、コピーをクラウドにアップロードします。 クラウドは、ファイルが悪意のあるか安全かを判断するかどうかに応じて、ファイルを実行したり、すべての将来の遭遇でブロックしたりする前に、追加の分析を実行して決定に到達します。

多くの場合、このプロセスでは、新しいマルウェアの応答時間を数時間から数秒に短縮できます。

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
> - ファイル ブロック レベルを High に設定 **すると** 、強力なレベルの検出が適用されます。 万が一、ファイルブロックによって正当なファイルが誤検知された場合は、検疫済み [ファイルを復元できます](./restore-quarantined-files-microsoft-defender-antivirus.md)。
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

4. [マップ] セクションで、[詳細な分析が必要な場合にファイル サンプルを送信する] をダブルクリックし、[有効] に **設定します**。 [詳細 **な分析が必要な場合にファイル サンプルを送信する] で、[** すべての **サンプルを送信**] を選択し **、[OK] をクリックします**。

5. 設定を変更した場合は、ネットワーク全体にグループ ポリシー オブジェクトを再展開して、すべてのエンドポイントが確実にカバーされます。

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a>個々のクライアントでブロックが一目で有効になっているか確認する

Windows のセキュリティ設定を使用して、個々のクライアントで一目でブロックが有効になっているか確認できます。

クラウド配信の保護と自動サンプル送信の両方が有効になっている限り、一目で **ブロックが自動的** に有効になります。

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

実際にブロックを一目で保護せずに前提条件の設定を保持する場合は、一目でブロックを無効にすることもできます。 遅延の問題が発生している場合や、ネットワークに対する機能の影響をテストする場合は、一時的にブロックをオフにできます。 ただし、一目でブロックを完全に無効にすることをお勧めしません。

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager でブロックを一目でオフにする

1. Microsoft Endpoint Manager 管理センター ( ) に移動 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) し、サインインします。

2. [エンドポイント セキュリティ **ウイルス対策**  >  **] に** 移動し、Microsoft Defender ウイルス対策ポリシーを選択します。

3. [管理 **] で**、[プロパティ] **を選択します**。

4. [構成設定 **] の横にある**[編集] **を選択します**。

5. 次の設定の 1 つ以上を変更します。

   - [ **クラウド配信の保護を有効にする] を** **[いいえ] または [構成** されていません **] に設定します**。
   - [ **クラウド配信の保護レベル] を [** 構成されていません **] に設定します**。
   - [Defender **Cloud Extended Timeout in Seconds] ボックスをオフ** にします。

6. 設定を確認して保存します。

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>グループ ポリシーで一目でブロックをオフにする

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターを使用して、[** コンピューターの構成] **に移動し、[** 管理 **用テンプレート] をクリックします**。

3. Windows コンポーネントの Microsoft Defender ウイルス **対策**  >  マップを **通じてツリーを**  >  **展開します**。

4. [一目 **でブロックする] 機能をダブルクリックし、** オプションを [無効] に **設定します**。

    > [!NOTE]
    > 一目でブロックを無効にしても、前提条件のグループ ポリシーは無効または変更されない。

## <a name="see-also"></a>関連項目

- [Windows 10 の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)

- [クラウドによる保護を有効にする](enable-cloud-protection-microsoft-defender-antivirus.md)