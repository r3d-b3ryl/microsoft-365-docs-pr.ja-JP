---
title: include ファイル
description: include ファイル
author: mjcaparas
ms.service: microsoft-365-enterprise
ms.author: macapara
ms.openlocfilehash: e8d19f8ab5423ccc0441d29efab2ecdb3eb27a04
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60677071"
---
## <a name="prerequisites"></a>前提条件

Microsoft Defender for Endpoint シナリオのセキュリティ管理の要件については、次のセクションを参照してください。

### <a name="environment"></a>環境

デバイスが Microsoft Defender for Endpoint にオンボードする場合:

- デバイスは、Configuration Manager または Intune のいずれかエンドポイント マネージャー既存のプレゼンスについて調査されます。
- プレゼンスが存在しないエンドポイント マネージャーセキュリティ管理機能を有効にする
- 信頼は、まだ存在しないAzure Active Directoryを使用して作成されます。
- Azure Active Directory信頼は、Intune (Intune) と通信しエンドポイント マネージャーポリシーを取得するために使用されます。
- ポリシーの取得エンドポイント マネージャー Microsoft Defender for Endpoint によってデバイスに適用されます。

### <a name="active-directory-requirements"></a>Active Directory の要件

ドメインに参加しているデバイスが、Azure Active Directoryとの信頼を作成すると、このシナリオはハイブリッド Azure Active Directory *と呼* ばれます。 Microsoft Defender for Endpoint のセキュリティ管理は、次の要件を満たすこのシナリオを完全にサポートします。

- Azure Active Directory Connect (AAD Connect) は、Microsoft Defender for Endpoint から使用されるテナントに同期する必要があります
- ハイブリッド Azure Active Directory参加は、環境で構成する必要があります (フェデレーションまたは同期AAD Connect)
- AAD Connect同期には、デバイス オブジェクトをスコープ内に含める必要があります (Azure Active Directoryに必要な場合)
- AAD Connect 2012 R2 の同期ルールを変更する必要があります (Server 2012 R2 のサポートが必要な場合)

### <a name="connectivity-requirements"></a>接続要件

デバイスは、次のエンドポイントにアクセスできる必要があります。

- `enterpriseregistration.windows.net`- 登録Azure AD。
- `login.microsoftonline.com`- 登録Azure AD。
- `*.dm.microsoft.com` - ワイルドカードを使用すると、登録、チェックイン、およびレポートに使用されるクラウド サービス エンドポイントがサポートされ、サービスの規模が拡大するに応じ変更される可能性があります。

### <a name="supported-platforms"></a>サポートされるプラットフォーム

Microsoft Defender for Endpoint セキュリティ管理のポリシーは、次のデバイス プラットフォームでサポートされています。

- Windows 10 Professional/Enterprise [(KB5006738 )](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)
- Windows Server 2012R2 と[Microsoft Defender for Down-Level デバイス](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- Windows Server 2016[デバイス用 Microsoft Defender Down-Levelする](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-functionality-in-the-modern-unified-solution-for-windows-server-2012-r2-and-2016-preview)
- WindowsServer 2019 [(KB5006744 を使用](https://support.microsoft.com/topic/october-19-2021-kb5006744-os-build-17763-2268-preview-e043a8a3-901b-4190-bb6b-f5a4137411c0))
- Windows Server 2022


### <a name="licensing-and-subscriptions"></a>ライセンスとサブスクリプション

Microsoft Defender for Endpoint のセキュリティ管理を使用するには、次の情報が必要です。

- Microsoft Defender for Endpoint のライセンスを付与するサブスクリプション (Microsoft 365 など)、または Microsoft Defender for Endpoint 専用のスタンドアロン ライセンス。 オプションの現在の情報については、「エンドポイント用 Microsoft Defender の最小 [要件」を参照してください](/microsoft-365/security/defender-endpoint/minimum-requirements)。

  *Microsoft* Defender for Endpoint ライセンスを付与するサブスクリプションは、管理者センターのエンドポイント セキュリティ ノードへのテナント アクセスMicrosoft エンドポイント マネージャー付与します。 エンドポイント セキュリティ ノードでは、デバイスの Microsoft Defender for Endpoint を管理し、デバイスの状態を監視するためのポリシーを構成および展開します。

## <a name="architecture"></a>アーキテクチャ

次の図は、Microsoft Defender for Endpoint セキュリティ構成管理ソリューションの概念的な表現です。


:::image type="content" alt-text="Microsoft Defender for Endpoint セキュリティ構成管理ソリューションの概念的表現" source="../security/defender-endpoint/images/mde-architecture.png":::


1. Microsoft Defender for Endpoint にオンボードされているデバイス。

2. 各デバイスとデバイス間で信頼が確立Azure AD。 デバイスに既存の信頼がある場合、その信頼が使用されます。 デバイスが登録されていない場合は、新しい信頼が作成されます。


3. デバイスは、デバイスAzure AD ID を使用して、ユーザーと通信エンドポイント マネージャー。 この ID を使用Microsoft エンドポイント マネージャーデバイスを対象とするポリシーを、チェックイン時に配布できます。

4. Defender for Endpoint はポリシーの状態をレポートし、ポリシーの状態を エンドポイント マネージャー。

## <a name="configure-your-tenant-to-support-microsoft-defender-for-endpoint-security-configuration-management"></a>Microsoft Defender for Endpoint Security Configuration Management をサポートするためにテナントを構成する

Microsoft Defender for Endpoint のセキュリティ構成管理を Microsoft エンドポイント マネージャー管理センターでサポートするには、各コンソールから通信を有効にする必要があります。

1. ポータルにサインイン[しMicrosoft 365 Defenderエンドポイント](https://security.microsoft.com/)構成管理設定スコープに移動し、セキュリティ設定管理のプラットフォーム  >    >    >  を有効にします。

   :::image type="content" source="../media/enable-mde-settings-management-defender.png" alt-text="Defender コンソールで Microsoft Defender for Endpoint の設定管理を有効にします。":::

2. 関連するユーザーが、Defender ポータルで役割を構成することで、Microsoft エンドポイント マネージャーまたはそれらのアクセス許可を付与するエンドポイント セキュリティ設定を管理するアクセス許可を持っている必要があります。 [ロールの追加  >  **設定]**  >  **項目に移動します**。

   :::image type="content" source="../media/add-role-in-mde.png" alt-text="Defender ポータルで新しい役割を作成します。":::

   > [!TIP]
   > 既存の役割を変更し、必要なアクセス許可を追加したり、Microsoft Defender for Endpoint で追加の役割を作成したりすることはできません。

3. 役割を構成する場合は、ユーザーを追加し、次の手順で [エンドポイントセキュリティ設定の管理] を **選択Microsoft エンドポイント マネージャー。**

   :::image type="content" source="../media/add-role.png" alt-text="設定を管理するためのアクセス許可をユーザーに付与します。":::

4. Microsoft エンドポイント マネージャー管理センター

5. [**エンドポイント セキュリティ** Microsoft Defender for Endpoint] を選択し、[エンドポイントに対する Microsoft Defender for Endpoint の適用を許可する  >  **] (プレビュー) を [オン]** に **設定します**。

   :::image type="content" source="../media/enable-mde-settings-management-mem.png" alt-text="管理センターで Microsoft Defender for Endpoint の設定管理Microsoft エンドポイント マネージャー有効にします。":::

   このオプションを *[オン*] に設定すると、Microsoft エンドポイント マネージャー によって管理されていない Microsoft Defender for Endpoint のプラットフォーム スコープ内のすべてのデバイスが、Microsoft Defender for Endpoint にオンボードされる資格があります。

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>デバイスを Microsoft Defender for Endpoint にオンボードする

Microsoft Defender for Endpoint では、オンボード デバイスに対して複数のオプションがサポートされています。 現在のガイダンスについては[、「Defender](/microsoft-365/security/defender-endpoint/security-config-management) for Endpoint」のドキュメントの「Windowsデバイスのオンボード ツールとメソッド」を参照してください。

Intune または Configuration Manager で管理するデバイスは、このシナリオではサポートされていません。

## <a name="create-azure-ad-groups"></a>グループAzure AD作成

Defender for Endpoint にデバイスをオンボードした後、Microsoft Defender for Endpoint のポリシーの展開をサポートするデバイス グループを作成する必要があります。

Microsoft Defender for Endpoint に登録されているが、Intune または Configuration Manager によって管理されていないデバイスを識別するには、次の方法を実行します。

1. [Microsoft エンドポイント マネージャー管理センター](https://go.microsoft.com/fwlink/?linkid=2109431)にサインインします。

2. [デバイス]  >  **[すべてのデバイス] に** 移動し、[管理] 列を **選択** してデバイスのビューを並べ替えます。

   Microsoft Defender for Endpoint にオンボードされ、登録されているが Intune または Configuration Manager によって管理されていないデバイスでは、[管理] 列に **Microsoft Defender for Endpoint** *が表示* されます。 これらは、Microsoft Defender for Endpoint のセキュリティ管理のポリシーを受け取るデバイスです。

これらのデバイスのグループは、Azure AD[管理](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)[センター内Microsoft エンドポイント マネージャー作成できます](/mem/intune/fundamentals/groups-add)。

## <a name="deploy-policy"></a>ポリシーを展開する

Microsoft Defender for Endpoint によって管理されるデバイスを含む 1 つ以上の Azure AD グループを作成した後、Microsoft Defender for Endpoint のセキュリティ管理に関する次のポリシーを作成し、それらのグループに展開できます。

- ウイルス対策
- ファイアウォール
- ファイアウォールルール
- エンドポイントの検出と応答

> [!TIP]
> 同じ設定を管理する複数のポリシーをデバイスに展開しないようにします。
>
> Microsoft エンドポイント マネージャーは、各エンドポイント セキュリティ ポリシーの種類の複数のインスタンスを同じデバイスに展開し、各ポリシー インスタンスはデバイスによって個別に受信されます。 したがって、デバイスは異なるポリシーから同じ設定に対して個別の構成を受け取り、競合が発生する可能性があります。 一部の設定 (ウイルス対策の除外など) はクライアントで結合され、正常に適用されます。

1. Microsoft エンドポイント マネージャー管理センター

2. [エンドポイント セキュリティ **] に移動** し、構成するポリシーの種類 (ウイルス対策またはファイアウォール) を選択し、[ポリシーの作成] **を選択します**。

3. 次のプロパティまたは選択したポリシーの種類を入力します。

   - ウイルス対策ポリシーの場合は、次の項目を選択します。
     - プラットフォーム: **Windows 10、Windows 11、Windows サーバー (プレビュー)**
     - プロファイル: **Microsoft Defender ウイルス対策 (プレビュー)**

   - ファイアウォール ポリシーの場合は、次の項目を選択します。
     - プラットフォーム: **Windows 10、Windows 11、Windows サーバー (プレビュー)**
     - プロファイル: **Microsoft Defender ファイアウォール (プレビュー)**

   - [ファイアウォール ルール] ポリシーで、次の項目を選択します。
     - プラットフォーム: **Windows 10、Windows 11、Windows サーバー (プレビュー)**
     - プロファイル: **Microsoft Defender ファイアウォール ルール (プレビュー)**

   - [エンドポイントの検出と応答] ポリシーで、次の項目を選択します。
     - プラットフォーム: **Windows 10、Windows 11、Windows サーバー (プレビュー)**
     - プロファイル: **エンドポイントの検出と応答 (プレビュー)**

4. **[作成]** を選択します。

5. [基本 **] ページで** 、プロファイルの名前と説明を入力し、[次へ] を選択 **します**。

6. [構成 **設定] ページ** で、このプロファイルで管理する設定を選択します。 設定の詳細については、その情報ダイアログを展開し、[詳細]リンクを選択して、オンライン ドキュメントの設定の CSP 情報を表示します。

   設定の構成が完了したら、**[次へ]** を選択します。

7. [割 **り当て]** ページで、このプロファイルAzure ADグループを選択します。 プロファイルの割り当ての詳細については、「[ユーザーおよびデバイス プロファイルの割り当て](/mem/intune/configuration/device-profile-assign)」を参照してください。

   [**次へ**] を選んで続行します。

   > [!TIP]
   >
   > - 割り当てフィルターは、セキュリティ構成管理プロファイルではサポートされていません。
   > - Microsoft Defender *for Endpoint* 管理には、デバイス オブジェクトだけが適用されます。 ユーザーのターゲット設定はサポートされていません。
   > - 構成されたポリシーは、エンドポイント クライアントMicrosoft Intune Microsoft Defender の両方に適用されます。

8. ポリシー作成プロセスを完了し、[レビューと作成] ページ **で** 、[作成] を **選択します**。 作成したプロファイルのポリシーの種類を選択すると、新しいプロファイルが一覧に表示されます。

9. ポリシーが割り当てられるのを待ち、ポリシーが適用されたという成功の兆候を表示します。

10. [Get-MpPreference](/powershell/module/defender/get-mppreference#examples)コマンド ユーティリティを使用して、設定がクライアント上でローカルに適用されるのを検証できます。

