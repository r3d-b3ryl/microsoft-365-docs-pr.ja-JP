---
title: ネットワーク保護を有効にする
description: グループ ポリシー、PowerShell、またはモバイル デバイス管理と構成マネージャーを使用してネットワーク保護を有効にします。
keywords: ANetwork の保護、悪用、悪意のある Web サイト、IP、ドメイン、ドメイン、有効化、有効にする
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 465a510ef25b0be0ba406c1265096476959d8c19
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/29/2021
ms.locfileid: "61218024"
---
# <a name="turn-on-network-protection"></a>ネットワーク保護を有効にする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

[ネットワーク保護](network-protection.md) は、従業員がアプリケーションを使用して、インターネット上でフィッシング詐欺、悪用、その他の悪意のあるコンテンツをホストする可能性のある危険なドメインにアクセスするのを防ぐのに役立ちます。 テスト環境 [でネットワーク保護](evaluate-network-protection.md) を監査して、ブロックするアプリを確認してから有効にできます。

[ネットワーク フィルター構成オプションの詳細について説明します。](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>ネットワーク保護が有効になっているか確認する

レジストリ エディターを使用して、ローカル デバイスでネットワーク保護が有効になっているか確認します。

1. タスク バーの **[スタート** ] ボタンを選択し **、「regedit」と** 入力してレジストリ エディターを開きます。

2. サイド **メニュー HKEY_LOCAL_MACHINE** を選択します。

3. 入れ子になったメニューを [**ソフトウェア** ポリシー] に移動し \> 、Microsoft **Windows Defender Windows Defender** \>  \>  \> **保護に** \> **移動します**。

キーが見つからない場合は、[**ソフトウェア** Microsoft] に移動し、[Exploit Guard \>  \>  \> **ネットワークWindows Defender Windows Defenderに** \> **移動します**。

4. デバイス上のネットワーク保護の現在の状態を表示するには **、[EnableNetworkProtection]** を選択します。

   - 0 または **Off**
   - 1、または **On**
   - 2、または **監査** モード

    :::image type="content" alt-text="ネットワーク保護レジストリ キー。" source="../../media/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.png" lightbox="../../media/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.png":::

## <a name="enable-network-protection"></a>ネットワーク保護を有効にする

次の方法を使用してネットワーク保護を有効にする。

- [PowerShell](#powershell)
- [モバイル デバイス管理 (MDM)](#mobile-device-management-mdm)
- [Microsoft エンドポイント マネージャー](#microsoft-endpoint-manager)
- [グループ ポリシー](#group-policy)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)

### <a name="powershell"></a>PowerShell

1. **[powershell]** と入力スタート メニュー **右クリックし**、[管理者Windows PowerShell **実行] を選択します**。

2. 次のコマンドレットを入力します。

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. オプション: 次のコマンドレットを使用して監査モードで機能を有効にします。

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    機能 `Disabled` の代わりに、 `AuditMode` または `Enabled` 機能をオフにする場合に使用します。

### <a name="mobile-device-management-mdm"></a>モバイル デバイスの管理 (MDM)

[./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender)構成サービス プロバイダー (CSP) を使用して、ネットワーク保護を有効または無効にするか、監査モードを有効にします。

### <a name="microsoft-endpoint-manager"></a>Microsoft エンドポイント マネージャー

1. 管理センターにサインインMicrosoft エンドポイント マネージャー ( https://endpoint.microsoft.com) .

2. [デバイス構成 **プロファイル**  >  **] [プロファイルの**  >  **作成] に移動します**。

3. [プロファイルの **作成] フライアウト** で **、[プラットフォーム** ] を選択し、[プロファイルの種類] を **[テンプレート** ] **として選択します**。

4. [テンプレート名 **] で**、テンプレート **の** 一覧から [エンドポイント保護] を選択し、[作成] を **選択します**。

4. [エンドポイント保護 **の**  >  **基本] に移動** し、プロファイルの名前を指定し、[次へ] を **選択します**。

5. [構成 **設定] セクション** で、[ネットワーク フィルターネットワークMicrosoft Defender Exploit Guard有効または監査]  >    >    >  **に****移動します**。 **[次へ]** を選択します。

6. 組織の **必要に応じて**、適切なスコープタグ、割 **り** 当て、適用ルールを選択します。 管理者は、より多くの要件を設定できます。

7. すべての情報を確認し、[作成] を **選択します**。

### <a name="group-policy"></a>グループ ポリシー

ドメインに参加しているコンピューターまたはスタンドアロン コンピューターでネットワーク保護を有効にするには、次の手順を使用します。

1. スタンドアロン コンピューターで、[スタート] に移動 **し、[グループ** ポリシーの編集] を入力して **選択します**。

    *-Or-*

    ドメインに参加しているグループ ポリシー管理コンピューターで、グループ [](https://technet.microsoft.com/library/cc731212.aspx)ポリシー管理コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。

2. **[グループ ポリシー管理エディター]** で、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。

3. ツリーを展開して **、Exploit Guard ネットワークWindows保護** \> **Microsoft Defender ウイルス対策Windows Defender** \> **コンポーネント** \> **を展開します**。

   > [!NOTE]
   > 以前のバージョンの Windowsでは、グループ ポリシー パスは "Windows Defender ウイルス対策" ではなく "Microsoft Defender ウイルス対策" と表示Microsoft Defender ウイルス対策。

4. [ユーザーとアプリによる **危険** な Web サイトへのアクセスを防止する] 設定をダブルクリックし、オプションを [有効] に **設定します**。 [オプション] セクションで、次のいずれかのオプションを指定する必要があります。
    - **ブロック** - ユーザーは悪意のある IP アドレスとドメインにアクセスできません。
    - **無効 (既定)** - ネットワーク保護機能が機能しません。 ユーザーは悪意のあるドメインへのアクセスをブロックされません。
    - **監査モード**- ユーザーが悪意のある IP アドレスまたはドメインにアクセスした場合、イベントはイベント ログWindowsされます。 ただし、ユーザーはアドレスへのアクセスをブロックされません。

   > [!IMPORTANT]
   > ネットワーク保護を完全に有効にするには、[グループ ポリシー] オプションを[有効]に設定し、[オプション] ドロップダウン メニューの [ブロック] を選択する必要があります。

レジストリ エディターを使用して、ローカル コンピューターでネットワーク保護が有効になっているか確認します。

1. [スタート **] を** 選択し **、「regedit」と** 入力してレジストリ **エディターを開きます**。

2. [ファイル] に **移動HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection\EnableNetworkProtection**

3. **[EnableNetworkProtection] を選択し**、値を確認します。
   - 0=Off
   - 1=On
   - 2=Audit

### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Configuration Manager コンソールを開きます。

2. Exploit Guard **の [アセットと**  >  **コンプライアンスEndpoint Protection Windows Defender**  >  **に移動します**。 

3. リボン **から [Exploit Guard ポリシーの作成** ] を選択して、新しいポリシーを作成します。
   - 既存のポリシーを編集するには、ポリシーを選択し、リボンまたは右クリック メニューから [プロパティ] を選択します。 [ネットワーク保護 **] タブから** [ネットワーク保護の構成 **] オプションを編集** します。  

4. [全般 **] ページ** で、新しいポリシーの名前を指定し、[ネットワーク保護] オプション **が有効になっているか** 確認します。 

5. [ネットワーク保護 **] ページ** で、[ネットワーク保護の構成] オプションで次のいずれかの **設定を選択** します。
   - **Block**
   - **監査**
   - **Disabled**
   
6. 残りの手順を完了し、ポリシーを保存します。 

7. リボンから [展開] **を選択** して、ポリシーをコレクションに展開します。

> [!IMPORTANT]
> Configuration Manager から Exploit Guard ポリシーを展開すると、展開を削除した場合、Exploit Guard の設定はクライアントから削除されません。 `Delete not supported` クライアントの Exploit Guard 展開を削除すると、Configuration Manager クライアントの ExploitGuardHandler.log に記録されます。 <!--CMADO8538577-->
> 次の PowerShell スクリプトを SYSTEM コンテキストで実行して、これらの設定を削除できます。<!--CMADO9907132-->
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

- [ネットワーク保護と TCP 3 ウェイ ハンドシェイク](network-protection.md#network-protection-and-the-tcp-three-way-handshake)

- [ネットワーク保護を評価する](evaluate-network-protection.md)

- [ネットワーク保護のトラブルシューティング](troubleshoot-np.md)
