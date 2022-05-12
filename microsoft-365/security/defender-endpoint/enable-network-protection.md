---
title: ネットワーク保護を有効にする
description: グループ ポリシー、PowerShell、またはモバイル デバイス管理とConfiguration Managerを使用してネットワーク保護を有効にします。
keywords: ネットワーク保護、悪用、悪意のある Web サイト、IP、ドメイン、ドメイン、有効化、有効にする
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.date: ''
ms.openlocfilehash: e53cda0ac61bdc546e972d663bf0063b02b21ad3
ms.sourcegitcommit: 570c3be37b6ab1d59a4988f7de9c9fb5ca38028f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2022
ms.locfileid: "65363267"
---
# <a name="turn-on-network-protection"></a>ネットワーク保護を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

> [!TIP]
> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

[ネットワーク保護](network-protection.md) は、フィッシング詐欺、悪用、その他の悪意のあるコンテンツをインターネット上でホストする可能性のある危険なドメインに、従業員がアプリケーションを使用してアクセスできないようにするのに役立ちます。 テスト環境で [ネットワーク保護を監査して、ネットワーク保護](evaluate-network-protection.md) を有効にする前にブロックされるアプリを確認できます。

[ネットワーク フィルターの構成オプションの詳細について説明します。](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>ネットワーク保護が有効になっているかどうかを確認する

レジストリ エディターを使用して、ローカル デバイスでネットワーク保護が有効になっているかどうかを確認します。

1. タスク バーの **[スタート]** ボタンを選択し、「 **regedit」** と入力してレジストリ エディターを開きます。

2. サイド メニューから **HKEY_LOCAL_MACHINE** を選択します。

3. 入れ子になったメニューから **ソフトウェア** \> **ポリシー** \> **Microsoft** \> **Windows Defender Windows Defender** \> **Exploit Guard** \> **Network Protection** に移動します。

キーが見つからない場合は、**ソフトウェア** \> **Microsoft** \> **Windows Defender Windows Defender** \> **Exploit Guard** \> **Network Protection** に移動します。

4. **EnableNetworkProtection を** 選択して、デバイス上のネットワーク保護の現在の状態を確認します。

   - 0、または **オフ**
   - 1、または **On**
   - 2、または **監査** モード

    :::image type="content" source="../../media/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.png" alt-text="Network Protection レジストリ キー" lightbox="../../media/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.png":::

## <a name="enable-network-protection"></a>ネットワーク保護を有効にする

次のいずれかの方法を使用してネットワーク保護を有効にします。

- [PowerShell](#powershell)
- [モバイル デバイス管理 (MDM)](#mobile-device-management-mdm)
- [Microsoft エンドポイント マネージャー](#microsoft-endpoint-manager)
- [グループ ポリシー](#group-policy)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)

### <a name="powershell"></a>PowerShell

1. スタート メニューに **「powershell**」と入力し、**Windows PowerShell** 右クリックして [**管理者として実行**] を選択します。

2. 次のコマンドレットを入力します。

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. 省略可能: 次のコマンドレットを使用して、監査モードで機能を有効にします。

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    機能の`AuditMode`代わりに使用`Disabled`するか、オフ`Enabled`にします。

### <a name="mobile-device-management-mdm"></a>モバイル デバイスの管理 (MDM)

[./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender) 構成サービス プロバイダー (CSP) を使用して、ネットワーク保護を有効または無効にするか、監査モードを有効にします。

ネットワーク保護を有効または無効にするか、監査モードを有効にする前に、[Microsoft Defender マルウェア対策プラットフォームを最新バージョンに更新](https://support.microsoft.com/topic/update-for-microsoft-defender-antimalware-platform-92e21611-8cf1-8e0e-56d6-561a07d144cc)します。


### <a name="microsoft-endpoint-manager"></a>Microsoft エンドポイント マネージャー

1. Microsoft エンドポイント マネージャー管理センター (https://endpoint.microsoft.com).

2. **[デバイス]** > **[構成プロファイル]** > **[プロファイルの作成]** に移動します。

3. [ **プロファイルの作成** ] ポップアップで、[ **プラットフォーム** ] を選択し、[ **プロファイルの種類** ] を **[テンプレート**] として選択します。

4. **テンプレート名** で、テンプレートの一覧から **[エンドポイント保護** の選択] を選択し、[**作成**] を選択します。

4. **Endpoint** **protectionBasics** >  に移動し、プロファイルの名前を指定して、[**次へ**] を選択します。

5. [**構成設定]** セクションで、**Microsoft Defender Exploit Guard** >  **Network filteringNetwork** >  **protectionEnable** >  または **Audit** に移動します。 **[次へ]** を選択します。

6. 組織で必要に応じて、適切な **スコープ タグ**、 **割り当て**、 **適用規則** を選択します。 管理者は、より多くの要件を設定できます。

7. すべての情報を確認し、[ **作成**] を選択します。

### <a name="group-policy"></a>グループ ポリシー

ドメインに参加しているコンピューターまたはスタンドアロン コンピューターでネットワーク保護を有効にするには、次の手順に従います。

1. スタンドアロン コンピューターで、[ **スタート]** に移動し、「 **グループ ポリシーの編集」** と入力して選択します。

    *-Or-*

    ドメインに参加しているグループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](https://technet.microsoft.com/library/cc731212.aspx)を開き、構成するグループ ポリシー オブジェクトを右クリックし、[**編集]** を選択します。

2. **[グループ ポリシー管理エディター]** で、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。

3. ツリーを展開して、**Exploit Guard** \> **Network 保護****Microsoft Defender ウイルス対策Windows Defender** \> **コンポーネント**\>をWindowsします。

   > [!NOTE]
   > 以前のバージョンのWindowsでは、グループ ポリシー パスに "Microsoft Defender ウイルス対策" ではなく "Windows Defender ウイルス対策" と表示される場合があります。

4. [ **ユーザーとアプリが危険な Web サイトにアクセスできないようにする** ] 設定をダブルクリックし、オプションを **[有効]** に設定します。 [オプション] セクションで、次のいずれかのオプションを指定する必要があります。
    - **ブロック** - ユーザーは悪意のある IP アドレスとドメインにアクセスできません。
    - **無効 (既定値)** - ネットワーク保護機能は機能しません。 ユーザーは悪意のあるドメインへのアクセスをブロックされません。
    - **監査モード** - ユーザーが悪意のある IP アドレスまたはドメインにアクセスした場合、イベントはWindows イベント ログに記録されます。 ただし、ユーザーがアドレスにアクセスすることはブロックされません。

   > [!IMPORTANT]
   > ネットワーク保護を完全に有効にするには、グループ ポリシー オプションを **[有効]** に設定し、[オプション] ドロップダウン メニューで **[ブロック**] を選択する必要があります。

   > [!NOTE]
   > オプション: [ネットワーク保護が有効になっているかどうかを確認](#check-if-network-protection-is-enabled)するの手順に従って、グループ ポリシーの設定が正しいことを確認します。

### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Configuration Manager コンソールを開きます。

2. **資産とコンプライアンス** > **Endpoint Protection Windows Defender** >  **Exploit Guard** に移動します。

3. リボンから **[Exploit Guard Policy の作成** ] を選択して、新しいポリシーを作成します。
   - 既存のポリシーを編集するには、ポリシーを選択し、リボンまたは右クリック メニューから **[プロパティ** ] を選択します。 [ **ネットワーク保護** ] タブから [ **ネットワーク保護** の構成] オプションを編集します。  

4. [ **全般** ] ページで、新しいポリシーの名前を指定し、 **ネットワーク保護** オプションが有効になっていることを確認します。

5. [ **ネットワーク保護** ] ページで、[ **ネットワーク保護の構成** ] オプションで次のいずれかの設定を選択します。
   - **Block**
   - **監査**
   - **Disabled**
   
6. 残りの手順を完了し、ポリシーを保存します。 

7. リボンで [ **展開** ] を選択し、ポリシーをコレクションに展開します。


> [!IMPORTANT]
> Configuration Managerから Exploit Guard ポリシーをデプロイすると、展開を削除しても、Exploit Guard の設定はクライアントから削除されません。 `Delete not supported`は、クライアントの Exploit Guard 展開を削除すると、Configuration Manager クライアントの ExploitGuardHandler.log に記録されます。 <!--CMADO8538577-->
> SYSTEM コンテキストで次の PowerShell スクリプトを実行して、これらの設定を削除できます。<!--CMADO9907132-->
>
> ```powershell
> $defenderObject = Get-WmiObject -Namespace "root/cimv2/mdm/dmmap" -Class "MDM_Policy_Config01_Defender02" -Filter "InstanceID='Defender' and ParentID='./Vendor/MSFT/Policy/Config'"
> $defenderObject.AttackSurfaceReductionRules = $null
> $defenderObject.AttackSurfaceReductionOnlyExclusions = $null
> $defenderObject.EnableControlledFolderAccess = $null
> $defenderObject.ControlledFolderAccessAllowedApplications = $null
> $defenderObject.ControlledFolderAccessProtectedFolders = $null
> $defenderObject.EnableNetworkProtection = $null
> $defenderObject.Put()
>
> $exploitGuardObject = Get-WmiObject -Namespace "root/cimv2/mdm/dmmap" -Class "MDM_Policy_Config01_ExploitGuard02" -Filter "InstanceID='ExploitGuard' and ParentID='./Vendor/MSFT/Policy/Config'"
> $exploitGuardObject.ExploitProtectionSettings = $null
> $exploitGuardObject.Put()
>```  

## <a name="see-also"></a>関連項目

- [ネットワーク保護](network-protection.md)

- [ネットワーク保護と TCP の 3 方向ハンドシェイク](network-protection.md#network-protection-and-the-tcp-three-way-handshake)

- [ネットワーク保護を評価する](evaluate-network-protection.md)

- [ネットワーク保護のトラブルシューティング](troubleshoot-np.md)
