---
title: グループ ポリシーを使用した Windows 10 デバイスのオンボード
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: グループ ポリシーを使用して、サービスにオンボードWindows 10デバイスに構成パッケージを展開します。
ms.openlocfilehash: 3329d21b4e0ba55c4b91a56a26af890b1199fb56
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60755736"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>グループ ポリシー Windows 10デバイスのオンボード 

**適用対象:**

- [Microsoft 365エンドポイント データ損失防止 (DLP)](./endpoint-dlp-learn-about.md)
- グループ ポリシー

> [!NOTE]
> グループ ポリシー (GP) 更新プログラムを使用してパッケージを展開するには、サーバー 2008 R2 以降Windowsする必要があります。

> サーバー Windows 2019 では、グループ ポリシーの基本設定で作成される XML ファイルの NT AUTHORITY\Well-Known-System-Account を NT AUTHORITY\SYSTEM に置き換える必要があります。

## <a name="onboard-devices-using-group-policy"></a>グループ ポリシーを使用してデバイスをオンボードする

1. サービス オンボーディング ウィザードから.zipした gp 構成 *パッケージ*(DeviceComplianceOnboardingPackage.zip) を開きます。 また、Microsoft コンプライアンス センターからパッケージ [を取得できます。](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. ナビゲーション ウィンドウで、[デバイス オンボーディング]**設定**  >  **を選択します**。

3. [展開方法 **] フィールドで** 、[グループ ポリシー] **を選択します**。

4. [パッケージ **のダウンロード] を** クリックし、.zip保存します。

5. デバイスからアクセスできる.zipファイルの内容を読み取り専用の共有場所に抽出します。 *OptionalParamsPolicy* というフォルダーと *DeviceComplianceLocalOnboardingScript.cmd というファイルが必要です*。

6. グループ ポリシー [管理コンソール](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] を **クリックします**。

7. グループ ポリシー **管理エディターで、[****コンピューターの構成**] 、[基本設定] の順に移動し、[コントロール パネルの **設定] に移動します**。

8. [スケジュールされたタスク **] を** 右クリックし、[新規] をポイントし、[イミディエイト タスク] (少なくとも Windows **7) をクリックします**。

9. 開く **[タスク]** ウィンドウで、[全般] タブ **に移動** します。[セキュリティ **オプション] で、[****ユーザーまたはグループの変更**] をクリックし、[SYSTEM] と入力し、[名前の確認] をクリック **して** **[OK] をクリックします**。 NT AUTHORITY\SYSTEM は、タスクが実行されるユーザー アカウントとして表示されます。

10. [ **ユーザーがログオンするかどうかを実行する] を選択し** 、[最高の特権で実行する **] チェック ボックスを** オンにします。

11. [操作] タブ **に移動し** 、[新規] **をクリックします。** [アクション **] フィールドで [プログラム** の開始] が選択 **されている必要** があります。 共有 *WindowsDefenderATPOnboardingScript.cmd* ファイルのファイル名と場所を入力します。

12. **[OK] を** クリックし、開いている GPMC ウィンドウを閉じます。

## <a name="offboard-devices-using-group-policy"></a>グループ ポリシーを使用してデバイスをオフボードする

セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。 デバイスに送信された期限切れのオフボード パッケージは拒否されます。 オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。

> [!NOTE]
> オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。

1. Microsoft コンプライアンス センターからオフボード パッケージ [を取得します](https://compliance.microsoft.com/compliancesettings/deviceonboarding)。

2. ナビゲーション ウィンドウで、[オンボーディング **/設定**  >  **オンボーディング]**  >  **を選択します**。

3. [展開方法 **] フィールドで** 、[グループ ポリシー] **を選択します**。

4. [パッケージ **のダウンロード] を** クリックし、.zip保存します。

5. デバイスからアクセスできる.zipファイルの内容を読み取り専用の共有場所に抽出します。 *-MM-DD.cmd DeviceComplianceOffboardingScript_valid_until_YYYYという名前のファイルが必要です*。

6. グループ ポリシー [管理コンソール](/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] を **クリックします**。

7. グループ ポリシー **管理エディターで、[****コンピューターの構成**] 、[基本設定] の順に移動し、[コントロール パネルの **設定] に移動します**。

8. [スケジュールされたタスク] **を右クリック** し、[新規] をポイント **し**、[イミディエイト タスク] **をクリックします**。

9. 開く **[タスク]** ウィンドウで、[全般] タブ **に移動** します。[セキュリティ オプション] の [ローカル SYSTEM ユーザー アカウント (BUILTIN\SYSTEM) **を選択します**。

10. [ **ユーザーがログオンするかどうかを実行する] を選択し** 、[最高の特権で実行する **]** チェック ボックスをオンにします。

11. [アクション] タブ **に移動し** 、[ **新規...] をクリックします**。[アクション **] フィールドで [プログラム** の開始] が選択 **されている必要** があります。 共有ファイルのファイル名と場所を  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd ファイルを入力* します。

12. **[OK] を** クリックし、開いている GPMC ウィンドウを閉じます。

> [!IMPORTANT]
> オフボードにより、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータは停止します。


## <a name="monitor-device-configuration"></a>デバイス構成の監視
グループ ポリシーでは、デバイス上のポリシーの展開を監視するオプションはありません。 監視は、ポータルまたはさまざまな展開ツールを使用して直接実行できます。

## <a name="monitor-devices-using-the-portal"></a>ポータルを使用してデバイスを監視する
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 コンプライアンス センター</a> にアクセスします。
2. [デバイス **一覧] を** クリックします。
3. デバイスが表示されているのを確認します。

> [!NOTE]
> デバイスが [デバイス] リストに表示を開始するには、数日 **かかる場合があります**。 これには、ポリシーがデバイスに配布される時間、ユーザーがログオンする前にかかる時間、エンドポイントがレポートを開始するのにかかる時間が含まれます。


## <a name="related-topics"></a>関連トピック
- [デバイスをWindows 10デバイスをオンボードMicrosoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-mdm.md)
- [ローカル スクリプトを使用した Windows 10 デバイスのオンボード](dlp-configure-endpoints-script.md)
- [非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード](dlp-configure-endpoints-vdi.md)
- [新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection オンボーディングの問題のトラブルシューティング](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)