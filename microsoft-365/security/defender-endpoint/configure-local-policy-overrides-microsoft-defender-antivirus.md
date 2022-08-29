---
title: Microsoft Defender ウイルス対策設定のローカル オーバーライドを構成する
description: Microsoft Defender ウイルス対策の設定をローカルで変更できないようにユーザーを有効または無効にします。
keywords: ローカル オーバーライド, ローカル ポリシー, グループ ポリシー, GPO, lockdown,merge, lists
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 08/02/2022
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 397fb835d73c2e18c3cc044f95d8b294e2ef762d
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67388168"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>ユーザーが Microsoft Defender ウイルス対策ポリシー設定をローカルで変更できないようにするか許可する


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

既定では、グループ ポリシー オブジェクトを介してネットワーク内のエンドポイントに展開される Microsoft Defender ウイルス対策設定では、ユーザーがローカルで設定を変更できなくなります。 この構成は、一部のインスタンスで変更できます。 たとえば、セキュリティ研究者や脅威調査担当者などの特定のユーザー グループが、使用するエンドポイントの個々の設定をさらに制御できるようにする必要がある場合があります。

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>Microsoft Defender ウイルス対策設定のローカル オーバーライドを構成する

これらのローカル オーバーライド ポリシーの既定の設定は **無効です**。

ポリシーが **[有効]** に設定されている場合、ユーザーは、Windows セキュリティ アプリ、ローカル [グループ ポリシー](microsoft-defender-security-center-antivirus.md)設定、または PowerShell コマンドレット (該当する場合) を使用して、デバイスに関連付けられている設定を変更できます。

[[設定] セクションの表](#table-of-settings)に、オーバーライド ポリシー設定と構成手順の一覧を示します。

これらの設定を構成するには、次の手順に従います。

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシーオブジェクトを右クリックし、[**編集]** を選択します。

2. [**グループ ポリシー管理エディター**] で、[**コンピューターの構成**] に移動し、[**管理用テンプレート**] を選択します。

3. ツリーを **Windows コンポーネント** > **Microsoft Defender ウイルス対策** に展開し、[設定セクションの表](#table-of-settings)で指定した **場所** (この記事では) を展開します。

4. 次の表に示すポリシー **設定** をダブルクリックし、目的の構成にオプションを設定します。 **[OK] を** 選択し、その他の設定についても繰り返します。

5. グループ ポリシー オブジェクトを通常どおりにデプロイします。

## <a name="table-of-settings"></a>設定の表

| 場所 | Setting | 記事 |
|---|---|---|---|
| マップ |Microsoft MAPS へのレポートのローカル設定のオーバーライドを構成する|[クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md) |
| Quarantine|検疫フォルダーからアイテムを削除するためのローカル設定のオーバーライドを構成する|[スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md) |
| リアルタイム保護|コンピューター上のファイルとプログラムのアクティビティを監視するためのローカル設定のオーバーライドを構成する|[Microsoft Defender ウイルス対策の常時オン保護と監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md) |
| リアルタイム保護|受信および送信ファイル アクティビティを監視するためのローカル設定のオーバーライドを構成する | [Microsoft Defender ウイルス対策の常時オン保護と監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md) |
| リアルタイム保護|ダウンロードしたすべてのファイルと添付ファイルをスキャンするためのローカル設定のオーバーライドを構成する|[Microsoft Defender ウイルス対策の常時オン保護と監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md) |
| リアルタイム保護|動作の監視を有効にするためのローカル設定のオーバーライドを構成する|[Microsoft Defender ウイルス対策の常時オン保護と監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md) |
| リアルタイム保護|リアルタイム保護を有効にするローカル設定のオーバーライドを構成する|[Microsoft Defender ウイルス対策の常時オン保護と監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 修復|スケジュールされたフル スキャンを実行して修復を完了するように、時刻のローカル設定のオーバーライドを構成する|[スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md) |
| スキャン|CPU 使用率の最大パーセンテージに対してローカル設定のオーバーライドを構成する|[スキャンを構成して実行する](run-scan-microsoft-defender-antivirus.md) |
| スキャン|スケジュール スキャン日のローカル設定のオーバーライドを構成する|[スケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| スキャン|スケジュールされたクイック スキャン時間のローカル設定のオーバーライドを構成する|[スケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| スキャン|スケジュールされたスキャン時間のローカル設定のオーバーライドを構成する|[スケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| スキャン|スケジュールされたスキャンに使用するスキャンの種類のローカル設定のオーバーライドを構成する|[スケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>ローカルおよびグローバルに定義された脅威の修復リストと除外リストをマージする方法を構成する

また、ローカルで定義されたリストをグローバルに定義されたリストと結合またはマージする方法を構成することもできます。 この設定は、 [除外リスト](configure-exclusions-microsoft-defender-antivirus.md)、 [指定された修復リスト](configure-remediation-microsoft-defender-antivirus.md)、攻撃 [面の縮小](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)に適用されます。

既定では、ローカル グループ ポリシーとWindows セキュリティ アプリで構成されたリストは、ネットワークにデプロイした適切なグループ ポリシー オブジェクトによって定義されたリストとマージされます。 競合がある場合は、グローバルに定義されたリストが優先されます。 この設定を無効にすると、グローバルに定義されたリスト (デプロイされた GPO など) のみが使用されるようにすることができます。

### <a name="use-group-policy-to-disable-local-list-merging"></a>グループ ポリシーを使用してローカル リストのマージを無効にする

1. グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシーオブジェクトを右クリックし、[編集] をクリック **します**。

2. [**グループ ポリシー管理エディター**] で、[**コンピューターの構成**] に移動し、[**管理用テンプレート**] を選択します。

3. ツリーを **Windows コンポーネント** > **Microsoft Defender ウイルス対策** に展開します。

4. **リストの [ローカル管理者のマージ動作の構成]** をダブルクリックし、オプションを **[無効]** に設定します。 次に [**OK**] を選びます。

### <a name="use-microsoft-endpoint-manager-to-disable-local-list-merging"></a>Microsoft エンドポイント マネージャーを使用してローカル リストのマージを無効にする

1. [Microsoft エンドポイント マネージャー管理センター](https://endpoint.microsoft.com)で、**エンドポイント セキュリティ** > **ウイルス対策** を選択します。

2. [ **ポリシーの作成**] を選択するか、既存の Microsoft Defender ウイルス対策ポリシーを変更します。

3. **[構成] 設定** で、[**ローカル 管理マージを無効にする**] の横にあるドロップダウンを選択し、[**ローカル 管理マージを無効にする**] を選択します。

> [!NOTE]
> ローカル リストのマージを無効にすると、フォルダー アクセスの制御設定がオーバーライドされます。 また、保護されたフォルダーや、ローカル管理者によって設定された許可されたアプリもオーバーライドされます。 フォルダー アクセスの制御設定の詳細については、「[Windows セキュリティでブロックされたアプリを許可する](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security)」を参照してください。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [Intune の Microsoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android 機能用 Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能用 Microsoft Defender for Endpoint を構成する](ios-configure-features.md)

## <a name="related-topics"></a>関連項目

- [Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview)
- [Windows の Microsoft Defender ウイルス対策](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender ウイルス対策を使用してエンド ユーザー操作を構成する](configure-end-user-interaction-microsoft-defender-antivirus.md)
