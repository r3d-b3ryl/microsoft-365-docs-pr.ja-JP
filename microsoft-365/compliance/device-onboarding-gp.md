---
title: グループ ポリシーを使用した Windows 10 および Windows 11 デバイスのオンボード
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: グループ ポリシーを使用して、構成パッケージをWindows 10およびWindows 11デバイスに展開し、サービスにオンボードします。
ms.openlocfilehash: 6c8c70d1bfdf3de0bc3848069a22b8610d445e42
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66623255"
---
# <a name="onboard-windows-10-devices-and-windows-11-using-group-policy"></a>グループ ポリシーを使用してWindows 10デバイスとWindows 11をオンボードする 

**適用対象:**

- [エンドポイントのデータ損失防止](./endpoint-dlp-learn-about.md)
- [インサイダー リスク管理](insider-risk-management.md)
- グループ ポリシー

> [!NOTE]
> グループ ポリシー (GP) 更新プログラムを使用してパッケージを展開するには、Windows Server 2008 R2 以降である必要があります。

> Windows Server 2019 の場合は、NT AUTHORITY\Well-Known-System-Account を、グループ ポリシー基本設定で作成される XML ファイルの NT AUTHORITY\SYSTEM に置き換える必要がある場合があります。

## <a name="onboard-devices-using-group-policy"></a>グループ ポリシーを使用してデバイスをオンボードする

1. [コンプライアンス センター](https://compliance.microsoft.com)を開きます。

2. ナビゲーション ウィンドウで、[**デバイスオンボード****の設定]** >  を選択します。

3. [ **展開方法]** フィールドで、[ **グループ ポリシー**] を選択します。

4. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

5. デバイスからアクセスできる読み取り専用の共有場所に、.zip ファイルの内容を抽出します。 *OptionalParamsPolicy* という名前のフォルダーと *DeviceComplianceLocalOnboardingScript.cmd* ファイルが必要です。

6. [グループ ポリシー管理コンソール](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、**［編集］** をクリックします。

7. **［グループ ポリシー管理エディター］** で、**［コンピューター構成］** に移動します。そして **［ユーザー設定］** をし、**［コントロール パネルの設定］** を行ないます。

8. **［スケジュールされたタスク］** を右クリックします。**［新規作成］** をポイントし、**［イミディエイト タスク］ (Windows 7 以上)** をクリックします。

9. **［タスク］** ウィンドウが開いたら、**［一般］** タブに移動します。**［セキュリティ オプション］** で、**［ユーザーまたはグループを変更］** をクリックし、「SYSTEM」と入力します。**［名前を確認］** をクリックし、**［OK］** をクリックします。 NT AUTHORITY\SYSTEM は、タスクを実行するユーザー アカウントとして表示されます。

10. **［ユーザーがログオンしているかどうかに関係なく実行する］** を選択し、**［最高の権限で実行する］** チェックボックスをオンにします。

11. **[アクション]** タブに移動し、[新規] をクリックします **。****[アクション****] フィールドで [プログラムの開始**] が選択されていることを確認します。 共有 *されている WindowsDefenderATPOnboardingScript.cmd* ファイルのファイル名と場所を入力します。

12. [ **OK] を** クリックし、開いている GPMC ウィンドウを閉じます。

## <a name="offboard-devices-using-group-policy"></a>グループ ポリシーを使用してデバイスをオフボードする
セキュリティ上の理由から、オフボード デバイスに使用されるパッケージは、ダウンロード日の 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボード ポリシーとオフボード ポリシーを同じデバイスに同時にデプロイすることはできません。そうしないと、予期しない競合が発生します。

1. [Microsoft Purview コンプライアンス ポータル](https://compliance.microsoft.com/compliancesettings/deviceonboarding)からオフボード パッケージを取得します。

2. ナビゲーション ウィンドウで、[**設定]****/[デバイス オンボーディング** > **オフボーディング**]  >  を選択します。

3. [ **展開方法]** フィールドで、[ **グループ ポリシー**] を選択します。

4. [ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。

5. デバイスからアクセスできる読み取り専用の共有場所に、.zip ファイルの内容を抽出します。 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* という名前のファイルが必要です。

6. [グループ ポリシー管理コンソール](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、**［編集］** をクリックします。

7. **グループ ポリシー管理エディター** で、[**コンピューターの構成]、[****基本設定]**、[**コントロール パネルの設定**] の順に移動します。

8. **[スケジュールされたタスク**] を右クリックし、[**新規**] をポイントして、[**イミディエイト タスク**] をクリックします。

9. 開いた **[タスク** ] ウィンドウで、[ **全般** ] タブに移動します。 **[セキュリティ オプション**] でローカル SYSTEM ユーザー アカウント (BUILTIN\SYSTEM) を選択します。

10. **[ユーザーがログオンしているかどうかを実行** する] を選択し、[**最高の特権で実行**] チェック ボックスをオンにします。

11. **[アクション]** タブに移動し、[**新規]...** をクリックします。**[アクション****] フィールドで [プログラムの開始**] が選択されていることを確認します。 共有  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* ファイルのファイル名と場所を入力します。

12. [ **OK] を** クリックし、開いている GPMC ウィンドウを閉じます。

> [!IMPORTANT]
> オフボードを使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータは停止します。


## <a name="monitor-device-configuration"></a>デバイス構成を監視する
グループ ポリシーでは、デバイス上のポリシーの展開を監視するオプションはありません。 監視は、ポータルで直接実行することも、さまざまなデプロイ ツールを使用して行うこともできます。

## <a name="monitor-devices-using-the-portal"></a>ポータルを使用してデバイスを監視する
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>に移動します。
2. [ **デバイス** ] の一覧をクリックします。
3. デバイスが表示されていることを確認します。

> [!NOTE]
> デバイスが [デバイス **] の一覧** に表示されるまでに数日かかる場合があります。 これには、ポリシーがデバイスに配布されるまでにかかる時間、ユーザーがログオンするまでにかかる時間、エンドポイントがレポートを開始するまでにかかる時間が含まれます。


## <a name="related-topics"></a>関連トピック
- [Microsoft Endpoint Configuration Managerを使用してWindows 10デバイスとWindows 11 デバイスをオンボードする](device-onboarding-sccm.md)
- [モバイル デバイス管理ツールを使用した Windows 10 および Windows 11 デバイスのオンボード](device-onboarding-mdm.md)
- [ローカル スクリプトを使用した Windows 10 および Windows 11 デバイスのオンボード](device-onboarding-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](device-onboarding-vdi.md)
- [新しくオンボードされたMicrosoft Defender for Endpoint デバイスで検出テストを実行する](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection のオンボードに関する問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
