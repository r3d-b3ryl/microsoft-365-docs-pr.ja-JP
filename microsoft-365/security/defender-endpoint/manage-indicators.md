---
title: インジケーターの作成
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義するファイル ハッシュ、IP アドレス、URL、またはドメインのインジケーターを作成します。
keywords: 管理、許可、ブロックされた、ブロック、クリーン、悪意のある、ファイル ハッシュ、ip アドレス、URL、ドメイン
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1e68e1e49dd855356840eb732c6050178ae1c147
ms.sourcegitcommit: 6c2ab5e8efe74d0dc2df610e2d9d2fdda8aaf074
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65669718"
---
# <a name="create-indicators"></a>インジケーターの作成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](/microsoft-365/security/defender-endpoint/defender-endpoint-plan-1)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
>
> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

侵害インジケーター (IoCs) マッチングは、すべてのエンドポイント保護ソリューションで不可欠な機能です。 この機能により、SecOps は検出およびブロック (防止と応答) のインジケーターの一覧を設定できます。

エンティティの検出、防止、除外を定義するインジケーターを作成します。 実行するアクションと、アクションを適用する期間とその時期、アクションを適用するデバイス グループの範囲を定義できます。

現在サポートされているソースは、Defender for Endpoint のクラウド検出エンジン、自動調査と修復エンジン、エンドポイント防止エンジン (Microsoft Defender ウィルス対策) です。

## <a name="cloud-detection-engine"></a>クラウド検出エンジン

Defender for Endpoint のクラウド検出エンジンは、収集されたデータを定期的にスキャンし、設定したインジケーターと一致するものを探します。 一致がある場合、IoC に指定した設定に従ってアクションが実行されます。

## <a name="endpoint-prevention-engine"></a>エンドポイント防止エンジン

インジケーターの同じリストは、防止エージェントによって適用されます。 つまり、Microsoft Defender AV が主な AV 構成である場合、一致したインジケーターは設定に従って処理されます。 たとえば、アクションが "Alert and Block (警告とブロック)" の場合、Microsoft Defender AV によってファイルの実行 (ブロックおよび修復) が防止され、対応する警告が発生します。 一方、アクションが "許可" に設定されている場合、Microsoft Defender AV ではファイルの検出やファイルの実行がブロックされません。

## <a name="automated-investigation-and-remediation-engine"></a>自動調査と修復エンジン

自動調査と修復は同じように動作します。 インジケーターが "許可" に設定されている場合、自動調査と修復では"悪い" 判定は無視されます。 "ブロック" に設定すると、自動調査と修復は、"悪い" として処理します。

EnableFileHashComputation 設定は、ファイル スキャン時に cert とファイル IoC のファイル ハッシュを計算します。 このポリシーは、信頼できるアプリケーションに属するハッシュと cert の IoC 適用をサポートしています。 ファイル設定の許可またはブロックで、同時に有効化、無効化できます。 EnableFileHashComputation はグループ ポリシーから手動で有効にでき、既定では無効になっています。

新しいインジケーター (IoC) を作成する場合は、次の 1 つ以上のアクションを使用できます。

- 許可 – IoC はデバイスで実行できます。
- 監査 – IoC の実行時にアラートがトリガーされます。
- 警告 – IoC は、ユーザーがバイパスできることを示す警告を表示します 
- ブロック実行 - IoC の実行は許可されません。
- ブロックと修復 - IoC の実行は許可されず、修復アクションが IoC に適用されます。

>[!NOTE]
> 警告モードを使用すると、危険なアプリを開くと、ユーザーに警告が表示されます。 プロンプトによってアプリの使用がブロックされることはありませんが、カスタム メッセージと、アプリの適切な使用方法を説明する会社のページへのリンクを指定できます。 ユーザーは引き続き警告をバイパスし、必要に応じてアプリを引き続き使用できます。 詳細については、「[Microsoft Defender for Endpointによって検出されたアプリを管理](/cloud-app-security/mde-govern)する」を参照してください。

次のインジケーターを作成できます。

- [ファイル](indicator-file.md)
- [IP アドレス、URL/ドメイン](indicator-ip-domain.md)
- [証明書](indicator-certificates.md)

次の表は、インジケーター (IoC) の種類ごとに使用可能なアクションを正確に示しています。

| IoC の種類 | 使用可能なアクション |
|:---|:---|
| [ファイル](indicator-file.md) | 許可 <br> 監査 <br> ブロックと修復 |
| [IP アドレス](indicator-ip-domain.md) | 許可 <br> 監査 <br> 実行をブロックする <br> 警告 |
| [URL とドメイン](indicator-ip-domain.md) | 許可 <br> 監査 <br> 実行をブロックする<br> 警告 |
| [証明書](indicator-certificates.md) | 許可 <br> ブロックと修復 |

既存の IoC の機能は変更されません。 ただし、現在サポートされている応答アクションと一致するようにインジケーターの名前が変更されました。

- "アラートのみ" 応答アクションの名前が "監査" に変更され、アラートの生成設定が有効になりました。
- "アラートとブロック" 応答の名前が、オプションのアラート生成設定を使用して "ブロックと修復" に変更されました。

IoC API スキーマと事前捜索の脅威 ID は、IoC 応答アクションの名前変更に合わせて更新されました。 API スキームの変更は、すべての IoC の種類に適用されます。

> [!Note]
> 1 テナントあたり 15,000 件のインジケーターの制限があります。 ファイルおよび証明書インジケーターは、[Microsoft Defender ウイルス対策ソフトウェア用に定義された例外](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)をブロックしません。 Microsoft Defender ウイルス対策はパッシブ モードの場合にインジケーターをサポートしません。
>
> 新しく更新されたアクションとアラートの設定に従って、新しいインジケーター (IoC) をインポートする形式が変更されました。 インポート パネルの下部にある新しい CSV 形式をダウンロードすることをお勧めします。

## <a name="related-topics"></a>関連トピック

- [コンテキスト IoC の作成](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [エンドポイント インジケーター API に Microsoft Defender を使用する](ti-indicator.md)
- [パートナー統合ソリューションの使用](partner-applications.md)
