# AWS::Location::Tracker<a name="aws-resource-location-tracker"></a>

The `AWS::Location::Tracker` resource specifies a tracker resource in your AWS account, which lets you receive current and historical location of devices\.

## Syntax<a name="aws-resource-location-tracker-syntax"></a>

To declare this entity in your AWS CloudFormation template, use the following syntax:

### JSON<a name="aws-resource-location-tracker-syntax.json"></a>

```
{
  "Type" : "AWS::Location::Tracker",
  "Properties" : {
      "[Description](#cfn-location-tracker-description)" : String,
      "[KmsKeyId](#cfn-location-tracker-kmskeyid)" : String,
      "[PositionFiltering](#cfn-location-tracker-positionfiltering)" : String,
      "[PricingPlan](#cfn-location-tracker-pricingplan)" : String,
      "[PricingPlanDataSource](#cfn-location-tracker-pricingplandatasource)" : String,
      "[TrackerName](#cfn-location-tracker-trackername)" : String
    }
}
```

### YAML<a name="aws-resource-location-tracker-syntax.yaml"></a>

```
Type: AWS::Location::Tracker
Properties: 
  [Description](#cfn-location-tracker-description): String
  [KmsKeyId](#cfn-location-tracker-kmskeyid): String
  [PositionFiltering](#cfn-location-tracker-positionfiltering): String
  [PricingPlan](#cfn-location-tracker-pricingplan): String
  [PricingPlanDataSource](#cfn-location-tracker-pricingplandatasource): String
  [TrackerName](#cfn-location-tracker-trackername): String
```

## Properties<a name="aws-resource-location-tracker-properties"></a>

`Description`  <a name="cfn-location-tracker-description"></a>
An optional description for the tracker resource\.  
*Required*: No  
*Type*: String  
*Minimum*: `0`  
*Maximum*: `1000`  
*Update requires*: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

`KmsKeyId`  <a name="cfn-location-tracker-kmskeyid"></a>
A key identifier for an [AWS KMS customer managed key](https://docs.aws.amazon.com/kms/latest/developerguide/create-keys.html)\. Enter a key ID, key ARN, alias name, or alias ARN\.  
*Required*: No  
*Type*: String  
*Minimum*: `1`  
*Maximum*: `2048`  
*Update requires*: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

`PositionFiltering`  <a name="cfn-location-tracker-positionfiltering"></a>
Specifies the position filtering for the tracker resource\.  
Valid values:  
+  `TimeBased` \- Location updates are evaluated against linked geofence collections, but not every location update is stored\. If your update frequency is more often than 30 seconds, only one update per 30 seconds is stored for each unique device ID\. 
+  `DistanceBased` \- If the device has moved less than 30 m \(98\.4 ft\), location updates are ignored\. Location updates within this area are neither evaluated against linked geofence collections, nor stored\. This helps control costs by reducing the number of geofence evaluations and historical device positions to paginate through\. Distance\-based filtering can also reduce the effects of GPS noise when displaying device trajectories on a map\. 
This field is optional\. If not specified, the default value is `TimeBased`\.  
*Required*: No  
*Type*: String  
*Allowed values*: `AccuracyBased | DistanceBased | TimeBased`  
*Update requires*: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

`PricingPlan`  <a name="cfn-location-tracker-pricingplan"></a>
Specifies the pricing plan for the tracker resource\.  
For additional details and restrictions on each pricing plan option, see the [Amazon Location Service pricing page](http://aws.amazon.com/location/pricing/)\.  
*Required*: Yes  
*Type*: String  
*Allowed values*: `MobileAssetManagement | MobileAssetTracking | RequestBasedUsage`  
*Update requires*: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

`PricingPlanDataSource`  <a name="cfn-location-tracker-pricingplandatasource"></a>
Specifies the data provider for the tracker resource\.  
+ Required value for the following pricing plans: `MobileAssetTracking `\| `MobileAssetManagement`
For more information about [Data Providers](http://aws.amazon.com/location/data-providers/), and [Pricing plans](http://aws.amazon.com/location/pricing/), see the Amazon Location Service product page\.  
Amazon Location Service only uses `PricingPlanDataSource` to calculate billing for your tracker resource\. Your data will not be shared with the data provider, and will remain in your AWS account or region unless you move it\.
Valid Values: `Esri` \| `Here`  
*Required*: No  
*Type*: String  
*Update requires*: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

`TrackerName`  <a name="cfn-location-tracker-trackername"></a>
The name for the tracker resource\.  
Requirements:  
+ Contain only alphanumeric characters \(A\-Z, a\-z, 0\-9\) , hyphens \(\-\), periods \(\.\), and underscores \(\_\)\.
+ Must be a unique tracker resource name\.
+ No spaces allowed\. For example, `ExampleTracker`\.
*Required*: Yes  
*Type*: String  
*Minimum*: `1`  
*Maximum*: `100`  
*Pattern*: `^[-._\w]+$`  
*Update requires*: [Replacement](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks-update-behaviors.html#update-replacement)

## Return values<a name="aws-resource-location-tracker-return-values"></a>

### Ref<a name="aws-resource-location-tracker-return-values-ref"></a>

When you pass the logical ID of this resource to the intrinsic `Ref` function, `Ref` returns the `Tracker` ARN\.

For more information about using the `Ref` function, see [Ref](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-ref.html)\.

### Fn::GetAtt<a name="aws-resource-location-tracker-return-values-fn--getatt"></a>

The `Fn::GetAtt` intrinsic function returns a value for a specified attribute of this type\. The following are the available attributes and sample return values\.

For more information about using the `Fn::GetAtt` intrinsic function, see [Fn::GetAtt](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/intrinsic-function-reference-getatt.html)\.

#### <a name="aws-resource-location-tracker-return-values-fn--getatt-fn--getatt"></a>

`Arn`  <a name="Arn-fn::getatt"></a>
The Amazon Resource Name \(ARN\) for the tracker resource\. Used when you need to specify a resource across all AWS\.  
+ Format example: `arn:aws:geo:region:account-id:tracker/ExampleTracker`

`CreateTime`  <a name="CreateTime-fn::getatt"></a>
The timestamp for when the tracker resource was created in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format: `YYYY-MM-DDThh:mm:ss.sssZ`\.

`TrackerArn`  <a name="TrackerArn-fn::getatt"></a>
Synonym for `Arn`\. The Amazon Resource Name \(ARN\) for the tracker resource\. Used when you need to specify a resource across all AWS\.  
+ Format example: `arn:aws:geo:region:account-id:tracker/ExampleTracker`

`UpdateTime`  <a name="UpdateTime-fn::getatt"></a>
The timestamp for when the tracker resource was last updated in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format: `YYYY-MM-DDThh:mm:ss.sssZ`\.