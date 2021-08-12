---
title: Microsoft Defender for Endpoint detections API フィールド
description: '[検出] API フィールドが、アプリ内の値にマップされるMicrosoft 365 Defender'
keywords: 検出、検出フィールド、フィールド、API、フィールド、プル検出、rest api、要求、応答
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a6bd4c687f398304e0c84c325fa53ac1a29253dc
ms.sourcegitcommit: 346c1332e1e9eebb5c90d6b8553dd70fcabf530a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53567910"
---
# <a name="microsoft-defender-for-endpoint-detections-api-fields"></a>Microsoft Defender for Endpoint detections API フィールド

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-apiportalmapping-abovefoldlink)

検出 API の一部として公開されるデータ フィールドと、そのデータ フィールドが検出 API にマップMicrosoft 365 Defender。

>[!Note]
>- [Defender for Endpoint Alert](alerts.md) は、1 つ以上の検出から構成されます。
>- **Microsoft Defender ATP 検出は** 、デバイスで発生した疑わしいイベントとその関連するアラートの詳細から **構成** されます。
>- Microsoft Defender for Endpoint Alert API は、アラートの使用に関する最新の API であり、各アラートに関連する証拠の詳細な一覧を含む。 詳細については、「Alert メソッドと[プロパティ」および「List alerts」](alerts.md)[を参照してください](get-alerts.md)。

## <a name="detections-api-fields-and-portal-mapping"></a>検出 API フィールドとポータル マッピング
次の表に、検出 API ペイロードで公開されている使用可能なフィールドの一覧を示します。 入力された値の例と、ポータルでのデータの反映方法に関する参照を示します。

[ArcSight] フィールド列には、Defender for Endpoint フィールドと ArcSight の組み込みフィールドとの間の既定のマッピングが含まれます。 SIEM 統合機能を有効にし、組織のニーズに合わせて変更できる場合は、ポータルからマッピング ファイルをダウンロードできます。 詳細については、「Defender [for Endpoint で SIEM 統合を有効にする」を参照してください](enable-siem-integration.md)。

フィールド番号は、以下の画像の数値と一致します。

> [!div class="mx-tableFixed"]
> 
> | ポータル ラベル | SIEM フィールド名 | ArcSight フィールド | 値の例 | 説明 |
> |------------------|----------------------|---------------------|---------------------|--------------------|
> | 1 | AlertTitle | name | Microsoft Defender AV が 「ミカッツ」 の重大度の高いマルウェアを検出しました | すべての検出で使用可能な値。 |
> | 2 | 重大度   | deviceSeverity | 高 | すべての検出で使用可能な値。 |
> | 3 | カテゴリ   | deviceEventCategory | マルウェア | すべての検出で使用可能な値。 |
> | 4  | 検出ソース | sourceServiceName   | ウイルス対策   | Microsoft Defender ウイルス対策または Defender for Endpoint。 すべての検出で使用可能な値。 |
> | 5  | MachineName  | sourceHostName | desktop-4a5ngd6 | すべての検出で使用可能な値。 |
> | 6  | FileName   | fileName   | Robocopy.exe | ファイルまたはプロセスに関連付けられた検出に使用できます。 |
> | 7  | FilePath   | filePath   | C:\Windows\System32\Robocopy.exe | ファイルまたはプロセスに関連付けられた検出に使用できます。 |
> | 8  | UserDomain | sourceNtDomain | CONTOSO  | Defender for Endpoint の動作ベースの検出に使用できる、アクティビティを実行しているユーザー コンテキストのドメイン。     |
> | 9  | UserName   | sourceUserName | liz.Bean | Defender for Endpoint の動作ベースの検出に使用できる、アクティビティを実行しているユーザー コンテキスト。 |
> | 10   | Sha1  | fileHash   | 3da065e07b990034e9db7842167f70b63aa5329 | ファイルまたはプロセスに関連付けられた検出に使用できます。 |
> | 11  | Sha256 | deviceCustomString6 | ebf54f745dc81e1958f75e4ca91dd0ab989fc9787bb6b0bf993e2f5    | Microsoft Defender AV 検出に使用できます。  |
> | 12   | Md5   | deviceCustomString5 | db979c04a99b96d370988325bb5a8b21 | Microsoft Defender AV 検出に使用できます。  |
> | 13  | ThreatName | deviceCustomString1  | HackTool:Win32/ミカッツ!dha   | Microsoft Defender AV 検出に使用できます。  |
> | 14   | IpAddress  | sourceAddress  | 218.90.204.141   | ネットワーク イベントに関連付けられた検出に使用できます。 たとえば、「悪意のあるネットワーク宛先への通信」などです。  |
> | 15  | Url   | requestUrl | down.esales360.cn    | ネットワーク イベントに関連付けられた検出に使用できます。 たとえば、「悪意のあるネットワーク宛先への通信」などです。   |
> | 16   | RemediationIsSuccess | deviceCustomNumber2 | TRUE   | Microsoft Defender AV 検出に使用できます。 ArcSight の値は、TRUE の場合は 1、FALSE の場合は 0 です。    |
> | 17   | WasExecutingWhileDetected | deviceCustomNumber1 | FALSE  | Microsoft Defender AV 検出に使用できます。 ArcSight の値は、TRUE の場合は 1、FALSE の場合は 0 です。    |
> | 18   | AlertId    | 外部ID | 636210704265059241_673569822 | すべての検出で使用可能な値。 |
> | 19  | LinkToWDATP  | flexString1    | `https://securitycenter.windows.com/alert/636210704265059241_673569822`   | すべての検出で使用可能な値。 |
> | 20  | AlertTime  | deviceReceiptTime   | 2017-05-07T01:56:59.3191352Z | イベントが発生した時刻。 すべての検出で使用可能な値。   |
> |  21  | MachineDomain    | sourceDnsDomain | contoso.com  | AAD 参加デバイスに関連しないドメイン名。 すべての検出で使用可能な値。   |
> | 22  | Actor | deviceCustomString4 | ボロン   | 既知のアクター グループに関連するアラートで使用できます。   |
> | 21+5    | ComputerDnsName  | マッピングなし | liz-bean.contoso.com | デバイスの完全修飾ドメイン名。 すべての検出で使用可能な値。  |
> |   | LogOnUsers | sourceUserId   | contoso\liz-Bean;  contoso\jay-hardee   | イベント時の対話型ログオン ユーザーのドメインとユーザー。 注: バージョン 1607 Windows 10デバイスの場合、ドメイン情報は使用できません。 |
> |   | InternalIPv4List | マッピングなし | 192.168.1.7, 10.1.14.1 | アクティブ なネットワーク インターフェイスの IPV4 内部 IPV4 の一覧。      |
> |   | InternalIPv6List | マッピングなし | fd30:0000:0000:0001:ff4e:003e:0009:000e, FE80:CD00:0000:0CDE:1257:0000:211E:729C | アクティブ なネットワーク インターフェイスの IPV6 内部 IPV6 の一覧。      |
| | LinkToMTP | マッピングなし | `https://securitycenter.windows.com/alert/da637370718981685665_16349121` | すべての検出で使用可能な値。
| | IncidentLinkToMTP | マッピングなし | `"https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM` | すべての検出で使用可能な値。
| | IncidentLinkToWDATP | マッピングなし | `https://securitycenter.windows.com/preferences2/integration/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM` | すべての検出で使用可能な値。
> | 内部フィールド | LastProcessedTimeUtc | マッピングなし | 2017-05-07T01:56:58.9936648Z | イベントがバックエンドに到着した時刻。 このフィールドは、検出が取得される時間範囲の要求パラメーターを設定するときに使用できます。 |
> |   | スキーマの一部ではない    | deviceVendor   |    | ArcSight マッピングの静的値 - 'Microsoft'。    |
> |   | スキーマの一部ではない    | deviceProduct  |    | ArcSight マッピングの静的値 - 'Microsoft Defender ATP'。 |
> |   | スキーマの一部ではない    | deviceVersion  |    | ArcSight マッピングの静的な値 - '2.0' は、マッピング バージョンの識別に使用されます。 |


:::image type="content" alt-text="数字を含むアラートのイメージ。" source="images/atp-alert-page.png" lightbox="images/atp-alert-page.png":::

:::image type="content" alt-text="番号を含むアラートの詳細ウィンドウのイメージ。" source="images/atp-siem-mapping13.png":::

:::image type="content" alt-text="数値 1 のアーティファクト タイムラインのイメージ。" source="images/atp-siem-mapping3.png" lightbox="images/atp-siem-mapping3.png":::

:::image type="content" alt-text="numbers2 のアーティファクト タイムラインのイメージ。" source="images/atp-siem-mapping4.png" lightbox="images/atp-siem-mapping4.png":::

:::image type="content" alt-text="イメージ マシン ビュー。" source="images/atp-mapping6.png" lightbox="images/atp-mapping6.png":::

:::image type="content" alt-text="イメージ ブラウザーの URL。" source="images/atp-mapping5.png" lightbox="images/atp-mapping5.png":::

:::image type="content" alt-text="イメージ アクターアラート。" source="images/atp-mapping7.png" lightbox="images/atp-mapping7.png":::


## <a name="related-topics"></a>関連トピック
- [エンドポイント向け Microsoft Defender で SIEM 統合を有効にする](enable-siem-integration.md)
- [エンドポイント検出用の Microsoft Defender をプルする ArcSight の構成](configure-arcsight.md)
- [REST API を使用したエンドポイント検出用の Microsoft Defender のプル](pull-alerts-using-rest-api.md)
- [SIEM ツール統合に関する問題のトラブルシューティング](troubleshoot-siem.md)
