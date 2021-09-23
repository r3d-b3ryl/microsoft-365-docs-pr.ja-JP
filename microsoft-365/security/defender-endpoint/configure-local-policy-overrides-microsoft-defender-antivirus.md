---
title: ユーザー設定のローカルオーバーライドをMicrosoft Defender ウイルス対策する
description: Microsoft Defender AV でユーザーがローカルで変更する設定を有効または無効にします。
keywords: ローカル オーバーライド, ローカル ポリシー, グループ ポリシー, gpo, lockdown,merge, lists
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 09/14/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 847b2085d6285299cea7f32f98c8c682dcb3fb4d
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2021
ms.locfileid: "59490155"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>ユーザーがポリシー設定をローカルで変更Microsoft Defender ウイルス対策または許可する


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

既定ではMicrosoft Defender ウイルス対策グループ ポリシー オブジェクトを介してネットワーク内のエンドポイントに展開される設定を使用すると、ユーザーはローカルで設定を変更できません。 これは、一部のインスタンスで変更できます。

たとえば、特定のユーザー グループ (セキュリティ研究者や脅威調査者など) が、使用するエンドポイントの個々の設定をさらに制御できる必要がある場合があります。

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>ユーザー設定のローカルオーバーライドをMicrosoft Defender ウイルス対策する

これらのポリシーの既定の設定は [無効] **です**。

[有効] に設定 **されている** 場合、エンドポイントのユーザーは、Windows セキュリティ アプリ、ローカル グループ ポリシー設定、および [PowerShell](microsoft-defender-security-center-antivirus.md)コマンドレット (必要に応じて) に関連付けられた設定を変更できます。

次の表に、各上書きポリシー設定と、関連する機能または設定の構成手順を示します。

これらの設定を構成するには、次の手順を実行します。

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。

3. ツリーを展開して **WindowsコンポーネントMicrosoft Defender ウイルス対策** し、次に設定の表  >  で **指定** した場所 (この記事) を展開します。

4. 下の表で指定 **したポリシー設定** をダブルクリックし、オプションを目的の構成に設定します。 **[OK] を** クリックし、他の設定を繰り返します。

5. グループ ポリシー オブジェクトを通常どおり展開します。

## <a name="table-of-settings"></a>設定の表

<br/><br/>

| Location | 設定 | 記事 |
|---|---|---|---|
| MAPS |Microsoft MAPS へのレポート用にローカル設定の上書きを構成する|[クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md) |
| 検疫する|検疫フォルダーからアイテムを削除するローカル設定の上書きを構成する|[スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md) |
| リアルタイム保護|コンピューター上のファイルとプログラムのアクティビティを監視するローカル設定の上書きを構成する|[常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md) |
| リアルタイム保護|受信および送信ファイルのアクティビティを監視するローカル設定の上書きを構成する | [常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md) |
| リアルタイム保護|ダウンロードしたファイルと添付ファイルをスキャンするローカル設定の上書きを構成する|[常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md) |
| リアルタイム保護|オンの動作監視用にローカル設定の上書きを構成する|[常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md) |
| リアルタイム保護|ローカル設定の上書きを構成してリアルタイム保護を有効にする|[常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md) |
| 修復|スケジュールされたフル スキャンを実行して修復を完了するために、時刻のローカル設定の上書きを構成する|[スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md) |
| スキャン|CPU 使用率の最大割合に対するローカル設定の上書きを構成する|[スキャンの構成と実行](run-scan-microsoft-defender-antivirus.md) |
| スキャン|スケジュール スキャン日のローカル設定の上書きを構成する|[スケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| スキャン|スケジュールされたクイック スキャン時間のローカル設定の上書きを構成する|[スケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| スキャン|スケジュールされたスキャン時間のローカル設定の上書きを構成する|[スケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| スキャン|スケジュールされたスキャンに使用するスキャンの種類のローカル設定の上書きを構成する|[スケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>ローカルおよびグローバルに定義された脅威の修復と除外リストの結合方法を構成する

ローカルに定義されたリストをグローバルに定義されたリストと結合または結合する方法を構成することもできます。 この設定は、除外リスト[、指定された](configure-exclusions-microsoft-defender-antivirus.md)修復リスト、攻撃表面[](configure-remediation-microsoft-defender-antivirus.md)[の縮小に適用されます](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)。

既定では、ローカル グループ ポリシーと Windows セキュリティ アプリで構成されているリストは、ネットワークに展開した適切なグループ ポリシー オブジェクトによって定義されたリストと結合されます。 競合がある場合は、グローバルに定義されたリストが優先されます。

この設定を無効にすると、グローバルに定義されたリスト (展開された GPO のリストなど) だけが使用されます。

### <a name="use-group-policy-to-disable-local-list-merging"></a>グループ ポリシーを使用してローカル リストのマージを無効にする

1. グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。

3. ツリーを展開して **、Windowsコンポーネント> Microsoft Defender ウイルス対策。**

4. [リストのローカル **管理者の差し込み動作を構成** する] をダブルクリックし、オプションを [無効] に **設定します**。 [**OK**] をクリックします。

> [!NOTE]
> ローカル リストの結合を無効にすると、フォルダー アクセスの制御設定が上書きされます。 また、ローカル管理者が設定した保護されたフォルダーまたは許可されたアプリも上書きされます。 フォルダー アクセスの制御設定の詳細については、「アプリでブロック[されたアプリ](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security)を許可する」を参照Windows セキュリティ。

## <a name="related-topics"></a>関連項目

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
- [ユーザーとのエンド ユーザー操作を構成Microsoft Defender ウイルス対策](configure-end-user-interaction-microsoft-defender-antivirus.md)
