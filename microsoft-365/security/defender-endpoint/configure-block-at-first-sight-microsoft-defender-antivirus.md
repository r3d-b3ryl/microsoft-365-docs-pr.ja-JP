---
title: 事前ブロックを有効にして、マルウェアを数秒で検出する
description: 事前ブロック機能を有効にして、数秒以内にマルウェアを検出してブロックします。
keywords: スキャン、事前ブロック、マルウェア、事前、クラウド、ディフェンダー、アンチウイルス
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 07/29/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 20918b3412a5534675c873fdfd9d2fb94a73ab75
ms.sourcegitcommit: ea4bc3b005d86b029700e56015a47b8cc6dca2a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2021
ms.locfileid: "58509943"
---
# <a name="turn-on-block-at-first-sight"></a>事前ブロックを有効にする

**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

この記事では、"事前ブロック" と呼ばれるウイルス対策/マルウェア対策機能について説明し、組織で事前ブロックを有効にする方法について説明します。

> [!TIP]
> この記事は、組織のセキュリティ設定を管理するエンタープライズ管理者および IT プロフェッショナルを対象としています。 エンタープライズ管理者や IT プロではないが、事前ブロックについて質問がある場合は、「[Not an enterprise admin or IT Pro? (エンタープライズ管理者またはITプロではありませんか?)](#not-an-enterprise-admin-or-it-pro)」を参照してください。

## <a name="what-is-block-at-first-sight"></a>"事前ブロック" とは？

事前ブロックは、数秒以内に新しいマルウェアを検出してブロックするための方法を提供する次世代の保護機能です。 特定のセキュリティ設定が有効になっている場合、事前ブロックが有効になります。 これには、以下の設定が含まれます。

- クラウドによる保護
- 指定されたサンプル送信タイムアウト (50 秒など) そして、
- 高のファイルブロックレベル。

ほとんどの企業組織では、事前ブロックを有効にするために必要な設定は、Microsoft Defender ウイルス対策の展開で構成されています。

## <a name="how-it-works"></a>メカニズム

Microsoft Defender ウイルス対策 は、疑わしいが検出されていないファイルを検出すると、クラウド保護バックエンドにクエリを実行します。 クラウド バックエンドでは、ヒューリスティックな機械学習による自動化されたファイル分析を適用して、悪意のあるファイルか、脅威ではないファイルかを判断します。

Microsoft Defender ウイルス対策は、複数の検出および防止テクノロジを使用して、正確でインテリジェントなリアルタイムの保護を提供します。

![Microsoft Defender AV エンジンのリスト](images/microsoft-defender-atp-next-generation-protection-engines.png)

> [!TIP]
> 詳細については、ブログ記事「[Microsoft Defender for Endpoint の次世代保護の中核となる高度なテクノロジについて」](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)を参照してください。

## <a name="a-few-things-to-know-about-block-at-first-sight"></a>事前ブロックについて知っておくべきいくつかのこと

- Windows 10 バージョン 1803 以降では、事前ブロックを実行すると、移植性のない実行可能ファイル (JS、VBS、マクロなど) と実行可能ファイルをブロックすることがあります。

- 事前ブロックでは、インターネットからダウンロードされた、またはインターネット ゾーンで発生した実行可能ファイルおよび非ポータブルの実行可能ファイルに対し、クラウド保護バックエンドのみが使用されます。 .exe ファイルのハッシュ値は、クラウド バックエンドを介してチェックされ、ファイルが以前に検出されなかったファイルであるかどうかが判断されます。

- クラウド バックエンドで判断できない場合、Microsoft Defender ウイルス対策によってファイルがロックされ、ファイルのコピーがクラウドにアップロードされます。 クラウドでさらに分析が実行されて判断が下された後は、そのファイルが危険か脅威でないかの判断に応じて、それ以降そのファイルの実行がすべて許可されるか、すべてブロックされます。

- 多くの場合、このプロセスによって、従来数時間かかっていた新しいマルウェアへの対応時間が数秒に短縮されます。

- クラウドベースの保護サービスによってファイルを分析する間、[ファイルが実行されないように抑制する時間の長さを指定する](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)こともできます。 また、ファイルがブロックされたときに[ユーザーのデスクトップに表示されるメッセージをカスタマイズする](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md)こともできます。 会社名、連絡先情報、メッセージの URL を変更することができます。

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>Microsoft Intune で事前ブロックを有効にする

> [!TIP]
> Microsoft Intune (現在は、Microsoft Endpoint Manager の一部)。.

1. Microsoft エンドポイント マネージャー管理センター (<https://endpoint.microsoft.com>) で、**[デバイス]** \> **[構成プロファイル]** に移動します。

2. **[デバイス制限]** プロファイル タイプを使用してプロファイルを選択または作成します。

3. [デバイス制限プロファイル] の **[構成設定]** で、**Microsoft Defender ウイルス対策** の次の設定を設定または確認します。

   - **クラウドによる保護**: 有効
   - **ファイル ブロック レベル**: 高
   - **クラウドによるファイル スキャンの時間延長**: 50
   - **サンプルを送信する前にユーザーに確認メッセージを表示する**: 確認メッセージを表示せずにすべてのデータを送信する

   :::image type="content" source="../../media/intune-block-at-first-sight.png" alt-text="Intune 構成ブロックを一目で確認する":::

4. 設定内容を保存します。

> [!TIP]
>
> - ファイルのブロック レベルを **[高]** に設定すると、強力な検出レベルが適用されます。 万一、ファイルのブロックによって正当なファイルが誤検出された場合、セキュリティ運用チームは[隔離されたファイルを復元](./restore-quarantined-files-microsoft-defender-antivirus.md)できます。
> - Intune での ≈ Defender ウイルス対策のデバイスの制限の構成について詳しくは、「[Microsoft Intune でデバイスの制限設定を構成する](/intune/device-restrictions-configure)」をご覧ください。
> - Intune での Microsoft Defender ウイルス対策のデバイスの制限の一覧については、「[Intune を使用して機能を許可または制限するように Windows 10 (以降) のデバイスを設定する](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)」をご覧ください。

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager で事前ブロックを有効にする

> [!TIP]
> Microsoft Endpoint Configuration Manager をお探しであれば、こちらは現在 Microsoft Endpoint Manager の一部になっています。

1. Microsoft エンドポイント マネージャー (<https://endpoint.microsoft.com>) で、**[Endpoint security]** \> **[Antivirus]** に移動します。

2. 既存のポリシーを選択するか、**Microsoft Defender ウイルス対策** のプロファイル タイプを使用して新しいポリシーを作成します。

3. 次の構成設定を設定または確認します。

   - **クラウドによる保護を有効にする**: はい
   - **クラウドによる保護レベル**: 高
   - **Defender クラウドの延長タイムアウト (秒単位)**: 50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="EndpointManagerでの事前ブロックの設定":::

4. Microsoft Defender ウイルス対策のプロファイルを、**[すべてのユーザー]**、**[すべてのデバイス]**、または **[すべてのユーザーとデバイス]** などのグループに適用します。

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>グループポリシーで事前ブロックを有効にする

> [!NOTE]
> Intune または Microsoft Endpoint Manager を使用して、事前ブロックを有効にすることをお勧めします。

1. グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. **[グループ ポリシー管理エディター]** を使用して、**[コンピューター構成]** \> **[管理用テンプレート]** \> **[Windows コンポーネント]** \> **[Microsoft Defender ウイルス対策]** \> **[MAPS]** に移動します。

3. [MAPS] セクションで、**[事前ブロックを構成する] 機能** をダブルクリックし、**[有効]** に設定して、**[OK]** を選択します。

    > [!IMPORTANT]
    > **[常に確認する] (0)** に設定すると、デバイスの保護状態が低下します。 **[送信しない] (2)** に設定すると、事前ブロックが動作しなくなります。

4. [MAPS] セクションで、**[詳細な分析が必要な場合はファイルのサンプルを送信する]** をダブルクリックし、**[有効]** に設定します。 **[詳細な分析が必要な場合はファイルのサンプルを送信する]** で、**[すべてのサンプルを送信]** を選択し、**[OK]** を選択します。

5. 通常どおり、ネットワーク全体にグループ ポリシー オブジェクトを再展開します。

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a>個別のクライアント デバイスで事前ブロックが有効であることを確認する

Windows セキュリティ アプリを使用して、個々のクライアント デバイスで事前ブロックが有効になっていることを確認できます。 事前ブロックは、**[クラウドベースの保護]** と **[サンプルの自動送信]** の両方が有効になっている限り、自動的に有効になります。

1. Windows セキュリティ アプリを開きます。

2. **[ウイルスと脅威保護]** を選択し、**[ウイルスと脅威保護設定]** で **[設定の管理]** を選択します。

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Windows セキュリティ アプリの [ウイルスと脅威の防止の設定] ラベルのスクリーンショット":::

3. **[クラウドベースの保護]** と **[サンプルの自動送信]** がオンになっていることを確認します。

> [!NOTE]
>
> - 前提条件の設定が構成され、グループ ポリシーを使って展開されている場合、このセクションで説明する設定は灰色表示され、個別のエンドポイントで使用できません。
> - グループ ポリシーを使った変更は、Windows の設定で設定を更新する前に、最初に個別のエンドポイントに展開する必要があります。

## <a name="validate-block-at-first-sight-is-working"></a>事前ブロックが機能していることを検証する

この機能が機能していることを検証するには、[事前ブロックのサンプル ファイル](https://demo.wd.microsoft.com/Page/BAFS)をダウンロードします。 ファイルをダウンロードするには、セキュリティ管理者ロールまたはグローバル管理者ロールが割り当てられている Azure AD のアカウントが必要です。

機能が機能していることを検証するには、「[ネットワークとクラウド間の接続を検証する](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)」のガイダンスに従ってください。

## <a name="turn-off-block-at-first-sight"></a>事前ブロックを無効にする

> [!CAUTION]
> 事前ブロックを無効にすると、デバイスとネットワークの保護状態が低下します。

事前ブロック保護を使用しないで、実際に前提条件の設定を保持する場合は、事前ブロックを無効にすることができます。 この機能がネットワークにどのように影響するかを確認するために、一時的に事前ブロックをオフにすることができます。 ただし、事前ブロックを完全に無効にすることはお勧めしません。

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager で事前ブロックを無効にする

1. Microsoft エンドポイント マネージャー管理センター (<https://endpoint.microsoft.com>) に移動してサインインします。

2. **[エンドポイント セキュリティ]** \> **[ウイルス対策]** に移動し、Microsoft Defender ウイルス対策ポリシーを選択します。

3. [**管理**] で [**プロパティ**] を選択します。

4. **[構成の設定]** の横にある **[編集]** を選択します。

5. 次の設定の 1 つ以上を変更します。

   - **[クラウドで配信される保護を有効にする]** を **[いいえ]** または **[未構成]** に設定します。
   - **[クラウド配信の保護レベル]** を **[未構成]** に設定します。
   - **Defender クラウドの延長タイムアウト (秒単位)** のチェック ボックスをオフにします。

6. 設定を確認して保存します。

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>グループ ポリシーで事前ブロックを無効にする

1. グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。

2. **[グループ ポリシー管理エディター]** を使用して、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。

3. **[Windows コンポーネント]** \> **[Microsoft Defender ウイルス対策]** \> **[MAPS]** の順にツリーを展開します。

4. **['事前ブロック' 機能を構成する]** をダブルクリックして、オプションを **[無効]** に設定します。

    > [!NOTE]
    > 事前ブロックを無効にしても、前提条件のグループ ポリシーが無効になったり変更されたりすることはありません。

## <a name="not-an-enterprise-admin-or-it-pro"></a>エンタープライズ管理者でも IT プロでもありませんか?

エンタープライズ管理者や IT Pro でなくても、事前ブロックについて質問がある場合は、このセクションが役に立ちます。 事前ブロックするは、マルウェアを数秒以内に検出してブロックする脅威保護機能です。 「事前ブロック」と呼ばれる特定の設定はありませんが、デバイスで特定の設定が構成されている場合、この機能は有効になります。

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a>自分のデバイスで事前ブロックをオンまたはオフに管理する方法

組織によって管理されていない個人用デバイスを使用している場合、事前ブロックを有効または無効にする方法を疑問に思うかもしれません。 Windows　セキュリティ　アプリを使用して、事前ブロックを管理できます。

1. Windows 10 コンピューターで、Windows セキュリティ アプリを開きます。

2. **[ウイルスと脅威の防止]** を選択します。

3. **[ウイルスと脅威保護設定]** で **[設定の管理]** を選択します。

4. 次のいずれかの手順を選択します。

   - 事前ブロックを有効にするには、**[クラウドベースの保護]** と **[サンプルの自動送信]** の両方がオンになっていることを確認してください。

   - 事前ブロックを無効にするには、**[クラウドベースの保護]** と **[サンプルの自動送信]** をオフにします。

     > [!CAUTION]
     > 事前ブロックをオフにすると、デバイスの保護レベルが低下します。 事前ブロックを完全に無効にすることはお勧めしません。


## <a name="see-also"></a>関連項目

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Windows セキュリティで保護を継続する](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
